---
layout: post
title: "How to debug eShopOnAbp in Visual Studio 2022"
subtitle: "This is for eShopOnAbp which was just updated to .NET 7, ABP 7, and Angular 15"
categories: [Programming]
tags: [ABP Framework, eShopOnAbp, .NET]
date: 2023-05-15 04:45:00 AM UTC
published: false
---


This is on a Windows machine; And for the version of eShopOnAbp which was just updated to .NET 7, ABP 7, and Angular 15: commit [f1c51a2](https://github.com/abpframework/eShopOnAbp/commit/f1c51a2a2777d8784868f13fb0d0646a0f52b42f)

## 0. Install the following

  - [Docker Desktop](https://www.docker.com/products/docker-desktop/)
  - Tye (follow [these steps](https://github.com/dotnet/tye/blob/main/docs/getting_started.md#installing-tye))


### Make sure Docker Desktop is running


### Make sure no *Docker Containers* or *Windows Services* are running on the default ports for the following
  - Postgres - port 5432
  - MongoDB - port 27017
  - Redis - port 6379
  - pgadmin - port 5050
  - keycloak - port 8080

For example, to stop currently running Postgres instance, open Windows Services app then look for `postgresql...`, then right-click on it, and click Stop.

![Services -> postgresql -> Stop](/images/2023/2023-05-11-1-services-postgresql-stop.png)


## 1. Clone the [eShopOnWeb](https://github.com/abpframework/eShopOnAbp) repository

I encountered the error `relation "AbpPermissionGroups" does not exist` when setting up the latest version of eShopOnAbp as of writing this blog post.

If you want to avoid that error, you can clone the project using [my fork of eShopOnAbp](https://github.com/jflaga/eShopOnAbp.git), then checkout the branch where I did a fix for that error by executing 

```
git clone https://github.com/jflaga/eShopOnAbp.git
git checkout fix/AbpPermissionGroups-error
```


### Rename `.env.example` file to `.env` file and provide PayPal ClientID and Secret.

Based on a comment [here](https://github.com/abpframework/eShopOnAbp/issues/166), you can use dummy data for PayPal ClientID and Secret if you don't want to test Checkout using Paypal.


## 2. Execute `run-tye.ps1`

This downloads the Docker images, creates containers, then builds the project.

**Wait until all applications are running.**


### Open the Tye dashboard ([http://localhost:8000](http://localhost:8000)) in a browser

Please read [eShopOnAbp's README](https://github.com/abpframework/eShopOnAbp#readme) for solutions to some errors you might encounter.



## 3. Start the Angular application

``` terminal
cd apps/angular
yarn
yarn start
```

## 4. Debug a microservice in Visual Studio

Please watch this video:

<iframe width="560" height="315" src="https://www.youtube.com/embed/fXz4RHOZnyg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<!-- [Debugging an eShopOnAbp microservice in Visual Studio 2022](https://youtu.be/fXz4RHOZnyg) -->



## 5. If you want to debug the Angular app

Please refer to [www.c-sharpcorner.com/article/debug-angular-in-vs-code/](https://www.c-sharpcorner.com/article/debug-angular-in-vs-code/)

