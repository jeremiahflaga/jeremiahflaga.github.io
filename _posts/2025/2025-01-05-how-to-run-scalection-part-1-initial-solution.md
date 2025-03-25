---
layout: post
title: "How to run Scalection project from Softaware, Part 1: Initial Solution"
date: 2025-01-05 12:00:00 AM UTC
# date_last_modified: 
dateLastUpdated:
category: Programming
tags: []
published: true
sidebar_content: <small><center><em>"Dare You to Move" by Switchfoot</em></center></small> <iframe width="100%" src="https://www.youtube.com/embed/iOTcr9wKC-o?si=eJ5zIoBndzGe30-7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
---

I had done some readings on System Design and wanted to find a related sample project written in ASP.NET Core which I can run locally.

I found [Scalection](https://github.com/softawaregmbh/scalection) from Softaware. This project has a corresponding [series of blog posts](https://softaware.at/codeaware/building-a-scalable-web-application-with-asp-net-core-and-azure-1) explaining the requirements of the project, and the evolution of the solution from the simple implementation to the one which solves scalability issues.
    
Part 1 to 2 of the series tackles the simple initial solution. It's corresponding code is in the `v1.initial` branch of the project's repository.

I checked out the branch `v1.initial` and tried to run the project in my local machine using Visual Studio 2022, but encountered some issues.

### Application Insights issue

The first issue I encountered was related to Application Insights. In the .NET Aspire Dashboard was this message: `"Configuration missing"`. And in the logs, `"Connection string parameter resource could not be used because connection string 'appinsights' is missing."`

![](/images/2025/2025-01-05-scalection-aspire-01-appinsights-conn-string-missing-error.png)

I did some googling, found the article ["Use Application Insights for .NET Aspire telemetry"](https://learn.microsoft.com/en-us/dotnet/aspire/deployment/azure/application-insights) from Microsoft, and solved the issue by adding this setting in `appsettings.json`. 

``` json
{
  ...,
  // TODO: store the value in app secrets
  "ConnectionStrings": {
    "appinsights": "InstrumentationKey=12345678-abcd-1234-abcd-1234abcd5678;IngestionEndpoint=https://westus3-1.in.applicationinsights.azure.com"
  }
}
```

Please note that the above connection string is just a dummy value. It makes the error go away, but it also removes the Application Insights functionality from the app. If you want this functionality in your local setup, you can search for how to setup Application Insights using an Azure free account.

Please note also that it is not proper to store connection strings in `appsettings.json`. These values should be stored as [app secrets](https://learn.microsoft.com/en-us/aspnet/core/security/app-secrets), and should not be included in your Git commits. I placed them in `appsettings.json` this time for convenience.


### SQL Server issue

After the `appinsights` issue was fixed, the .NET Aspire Dashboard indicated that all resources were running fine. 

![](/images/2025/2025-01-05-scalection-aspire-02-all-running.png)

But when I clicked on the endpoint for the `apiservice` project (https://localhost:7312/election in my case), I came across this error.

``` json
{
  "type": "https://tools.ietf.org/html/rfc9110#section-15.6.1",
  "title": "An error occurred while processing your request.",
  "status": 500
}
```

At this point, I suspected that this might have something to do with the database, because I had seen the database migration project in the Visual Studio solution but had not done anything related to db migration yet.

So I looked at the logs of the `sqlserver` resource, and lo and behold this error confronted me: `"Login failed for user 'sa'. Reason: Password did not match that for the login provided."`

Did some googling again and solved it through the article [".NET Aspire SQL Server integration"](https://learn.microsoft.com/en-us/dotnet/aspire/database/sql-server-integration), and through [a discussion on the Aspire GitHub repository](https://github.com/dotnet/aspire/discussions/4770#discussioncomment-9948728).

The solution was to add the SQL Server password in `appsettings.json`. (Same as with the Application Insights connection string above, this value should be saved as [app secret](https://learn.microsoft.com/en-us/aspnet/core/security/app-secrets).)

``` json
{
  ...,
  // TODO: store the value in app secrets
  "Parameters:sqlserver-password": "your-sql-server-password"
}
```

As the article linked to above says, the name of the parameter `sqlserver-password` is a formatting of the Aspire resource name (`sqlserver` in this case) with a `-password` suffix.

After doing that, I modified `Program.cs` of the `Scalection.AppHost` project and replaced `.WithDataVolume()` with the below code:

``` diff
var sqlDB = builder.AddSqlServer(ServiceDiscovery.SqlServer)
-           .WithDataVolume()
+           .WithDataVolume(name: "sqldbdatavolume", isReadOnly: false)
            .PublishAsAzureSqlDatabase()
            .AddDatabase(ServiceDiscovery.SqlDB);
```

### DB Migration

Finally, I run the project again; opened `app.http` under `Scalection.ApiService` project in Visual Studio 2022, then clicked on "Send request" for `POST {{migrationurl}}/sql/migrate` to run database migration.

![](/images/2025/2025-01-05-scalection-vs2022-db-migration-through-http-request.png)




### Disclaimer

Please note that my goal in this exploration was not to discover the _correct_ way of setting up the Scalection project. My goal was only to _successfully_ run the project on my local machine. If you think I did something wrong in any of the steps above, please say so in the comments section.

Thanks, and have fun coding.
