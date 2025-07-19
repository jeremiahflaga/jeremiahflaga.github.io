---
layout: post
title: 'Respawn with PostgreSQL error: PostgresException: 42P01: relation "sys.tables" does not exist'
excerpt: 
date: 2025-07-19 12:00:00 PM UTC
dateLastUpdated:
sidebar_content: '<small><small><center><em>"Gone (Our Version)" by Switchfoot</em></center></small></small> <iframe width="100%" src="https://www.youtube.com/embed/N2D_2RFRISg?si=IATQLQ7WMritD5yq" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>'
categories:
  - Programming
tags: 
  - Respawn
  - Postgres
---

Be sure to put the `DbAdapter = DbAdapter.Postgres` option, like this:

``` csharp
_respawner = await Respawner.CreateAsync(_conn, new RespawnerOptions
{
    DbAdapter = DbAdapter.Postgres,
    ...
});
```
