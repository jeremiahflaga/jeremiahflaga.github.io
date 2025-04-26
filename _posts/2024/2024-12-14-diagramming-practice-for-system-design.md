---
layout: post
title: "Diagramming Practice for System Design"
date: 2024-12-14 12:00:00 AM UTC
# date_last_modified: 
dateLastUpdated: 2025-04-27 12:00:00 AM UTC
categories: [Programming]
tags: []
published: true
sidebar_content: <small><small><center><em>"Dare You to Move" by Switchfoot</em></center></small></small> <iframe width="100%" src="https://www.youtube.com/embed/iOTcr9wKC-o?si=eJ5zIoBndzGe30-7" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
author_name: Jboy
enable_mermaid_diagram: true
---

> "Make copies, young man, many copies. You can only become a good artist by copying the masters." — Jean-Auguste-Dominique Ingres

> "It's not aping or slavish emulation to immerse ourselves in the works of the masters to the point of copying them line-for-line. The masters did it themselves, studying earlier masters." — Steven Pressfield

--------


I have been studying system design and figured that one of the more essential activities in system design is creating diagrams.

Creating diagrams reminds me of UML. I tried to learn UML a decade ago, but because I have not put into constant use what I learned, it has faded into oblivion.*

But now that I have the need to create diagrams, I have to relearn UML. Along with it, I need to familiarize myself with this newer diagramming approach called [The C4 Model](https://c4model.com/) which I encountered while exploring the GitHub repository ["Modular Monolith with DDD"](https://github.com/kgrzybek/modular-monolith-with-ddd). 

Based on my own experience and the experiences of others, a good thing to do when learning something is to copy the masters. So that's what I will do with regards to diagramming --- imitate the C4 and UML diagrams made by the masters. I'll be posting in this blog the resulting works.

--------

#### 1. System Context Diagram for Internet Banking System

Copied from Simon Brown's slides for his talk ["Visualising software architecture with the C4 model"](https://www.youtube.com/watch?v=x2-rSnhpw0g)


{: .img-responsive .col-lg-6 .col-sm-12 }
![System Context Diagram for Internet Banking System](/images/2024/2024-12-12-system-context-diagram-for-internet-banking-system.png)

--------


#### 2. Component Diagram for Internet Banking System

Copied from Simon Brown's slides for his talk ["Visualising software architecture with the C4 model"](https://www.youtube.com/watch?v=x2-rSnhpw0g)

{: .img-responsive .col-12 }
![Component Diagram for Internet Banking System](/images/2024/2024-12-14-container-diagram-for-internet-banking-system.png)

--------


#### 3. Streamy Domain Model

From the book "Creating Software with Modern Diagramming Techniques: Build Better Software with Mermaid" by Ashley Peacock

``` mermaid
---
title: Streamy Domain Model
---
classDiagram
    Title "1..*" -- "1..*" Genre: is associated with
    Title "1" *-- "0..*" Season: has
    Title "1" *-- "0..*" Review: has
    Title "0..*" o-- "1..*" Actor: has
    TV Show --|> Title: implements
    Short --|> Title: implements
    Film --|> Title: implements
    Viewer "0..*" --> "0..*" Title: watches
    Season "1" *-- "0..*" Review: has
    Season "1" *-- "1..*" Episode: has
    Episode "1" *-- "0..*" Review: has
```

``` mermaid

---
title: User Sign Up Flow
---
sequenceDiagram
    autonumber
    actor Browser
    participant Sign Up Service
    participant User Service
    participant Kafka
    
    Browser->>Sign Up Service: GET /sign_up
    activate Sign Up Service
    Sign Up Service-->>Browser: 200 OK (HTML page)
    deactivate Sign Up Service
    
    Browser->>+Sign Up Service: POST /sign_up
    Sign Up Service->>Sign Up Service: Validate input
    
    alt invalid input
        Sign Up Service-->>Browser: Error
    else valid input
        Sign Up Service->>+User Service: POST /users
        User Service--)Kafka: User Created Event Published
        Note left of Kafka: other services take action based on this event
        User Service-->>-Sign Up Service: 201 Created (User)
        Note over User Service, Kafka: sample note spanning two nodes, sample note spanning two nodes
        Sign Up Service-->>-Browser: 301 Redirect (Login page)
    end
```

--------

<div class="small" markdown="1">

**Footnotes:**

* In a recent interview, Grady Booch, the co-creator of UML, has an explanation for why many software projects today do not make use of UML. (Interview title on YouTube: ["Evolution of software architecture with the co-creator of UML (Grady Booch)"](https://www.youtube.com/watch?v=u7WaC429YcU&t=4873s) by The Pragmatic Engineer).

</div>
