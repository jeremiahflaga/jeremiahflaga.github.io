---
layout: post
title: 'OAuth2 has an abstract protocol flow'
excerpt: 
date: 2026-01-24 03:45:00 PM UTC
dateLastUpdated:
sidebar_content: ''
categories:
  - Programming
tags: 
  - OAuth

---

Many months ago, I tried reading "Mastering API Architecture: Design, Operate, and Evolve API-Based Systems" which I had bought from HumbleBundle.com. But after reading the first two chapters, I realized that it was not a hands-on kind of book. So I decided to stop reading it.

But the title of Chapter 7 caught my attention: "API Authentication and Authorization". So I read it, and from there I learned that OAuth2 has an abstract protocol on how OAuth2 grants should work:


<pre>
┌──────────────────────────────────────────────────────────────┐
│                    OAuth 2.0 Abstract Flow                   │
└──────────────────────────────────────────────────────────────┘

  ┌─────────┐                                   ┌─────────────┐
  │         │  (A) Authorization Request        │             │
  │         │ ───────────────────────────────>  │  Resource   │
  │         │                                   │    Owner    │
  │         │  (B) Authorization Grant          │   (User)    │
  │         │ <───────────────────────────────  │             │
  │         │                                   └─────────────┘
  │         │
  │         │
  │         │                                   ┌─────────────┐
  │ Client  │  (C) Authorization Grant          │             │
  │ (Your   │ ───────────────────────────────>  │Authorization│
  │  App)   │                                   │   Server    │
  │         │  (D) Access Token                 │             │
  │         │ <───────────────────────────────  │             │
  │         │       (+ Refresh Token)           └─────────────┘
  │         │
  │         │
  │         │                                   ┌─────────────┐
  │         │  (E) Access Token                 │             │
  │         │ ───────────────────────────────>  │  Resource   │
  │         │                                   │   Server    │
  │         │  (F) Protected Resource           │   (API)     │
  │         │ <───────────────────────────────  │             │
  └─────────┘                                   └─────────────┘
</pre>

I think that knowing about this abstract protocol flow helps in reducing confusion when trying to understand the implementation of the various grant types in OAuth2. So I'm leaving this to help remind myself of this in case I need to learn more about OAuth grants in the future.
