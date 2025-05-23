---
layout: post
title: "How to use Testcontainers and Postgres in the tests for ABP Framework's Application Services"
excerpt: ""
date: 2023-08-27 02:45:00 PM UTC
dateLastUpdated: 2024-02-25 01:20:00 PM UTC
categories:
  - Programming
tags: 
  - Testcontainers
  - DotNet.Testcontainers
  - ABP Framework
  - ABP.IO Platform
  - ASP.NET
published: true
---

<br />

**Update:**

Please refer to [this answer](https://github.com/abpframework/abp/discussions/17490#discussioncomment-8557112) from the GitHub Discussions page of ABP:

> The best method I found is to follow the same architecture used in MongoDB tests, which is using xunit's Collection Fixtures: ...
>  
> --- by @ahmednfwela

<br />


-----

I first learned about [Testcontainers](https://github.com/testcontainers/testcontainers-dotnet) from Nick Chapsas' video titled ["The cleanest way to use Docker for testing in .NET"](https://www.youtube.com/watch?v=01ZMTkoAhyM).

I tried to figure out how to use it (instead of the default in-memory Sqlite database) in running the tests for AppServices in a sample [ABP](https://github.com/abpframework/abp) project. I was able to successfully run the tests by modifying `EntityFrameworkCoreTestModule` to look like this:


``` csharp
[DependsOn(
    typeof(SampleTestBaseModule),
    typeof(SampleEntityFrameworkCoreModule),
    typeof(AbpEntityFrameworkCorePostgreSqlModule)
    )]
public class SampleEntityFrameworkCoreTestModule : AbpModule
{
    private readonly PostgreSqlContainer _postgreSqlContainer = new PostgreSqlBuilder().Build();

    public override void PreConfigureServices(ServiceConfigurationContext context)
    {
        _postgreSqlContainer.StartAsync().GetAwaiter().GetResult();
    }

    public override void ConfigureServices(ServiceConfigurationContext context)
    {
        var connectionString = _postgreSqlContainer.GetConnectionString();
        new SampleDbContext(
            new DbContextOptionsBuilder<SampleDbContext>().UseNpgsql(connectionString).Options
        ).GetService<IRelationalDatabaseCreator>().CreateTables();

        Configure<AbpDbContextOptions>(options =>
        {
            options.Configure(abpDbContextConfigurationContext =>
            {
                abpDbContextConfigurationContext.DbContextOptions.UseNpgsql(connectionString);
            });
        });
    }

    public override void OnApplicationShutdown(ApplicationShutdownContext context)
    {
        _postgreSqlContainer.StopAsync().GetAwaiter().GetResult();
    }
```

Note: I tried to use the async versions of the overriden methods, `PreConfigureServicesAsync` and `OnApplicationShutdownAsync`, but they were not working.

### Disclaimer

I'm new to ABP. If you see something wrong in that code, or if you see some potential issues I might encounter with that kind of code, please say so in the comments section.

Thanks.
