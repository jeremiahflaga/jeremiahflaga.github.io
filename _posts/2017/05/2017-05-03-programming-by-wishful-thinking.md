---
layout: post
title: Programming by wishful thinking and why we need to read
category: Programming
tags: [Programming, Harold Abelson, Gerald Jay Sussman, Book]
date: 2017-05-03 12:00:00 PM UTC
---

<!-- May 3, 2017 08:00:00 PM Philippine Time -->

Having been influenced by the idea of TDD (even though I have never used it in a project at work) and the idea of ["respecting levels of abstraction"](https://simpleprogrammer.com/2017/01/27/respecting-abstraction/), (and the Clean Code book of course), in my recent tasks at work, because we do not have unit tests, I just make myself imagine that the UI layer (the Presenters, Controllers, etc.) contains the tests.

<!--more-->

Then I try to start writing code on the user interface level of the app (the Presenters, Controllers, etc.).

I then ask myself, _"At this layer in the app, how do I want my classes and methods/functions to look like?"_

Then I try to call functions (which are not yet implemented) with as little set of parameters as possible -- only those parameters that I think are needed at this particular point in the app.


For example, at the level of the user interface (the Presenter, Controller, etc.), I start to call functions like this...

``` java
bookmark(item); or item.bookmark();
```

... or this ...

``` java
int numberOfItems = someObject.getNumberOfItemsOn(date);
```

... even though they are not yet implemented.

<!--
<div class="message">
At the user interface level, I want to avoid doing something like this:

<p>
<pre>
<code class="highlighter-rouge">
int steps = someObject.getSteps(date, acessToken, etc.);
</code>
</pre>
</p>

... with an access token passed to the `getSteps()` function, 

...because at this point, I do not want to care about <i>"how"</i> I get the number of steps from somewhere. At this point, I only care about getting the number of steps -- the <i>"what"</i>.
</div>
-->

When they look good already, I start to implement them.

``` java
public class SomeObject {

    ...

    public SomeObject(..., ...) {
        ...
    }

    public int getNumberOfItemsOn(Date date) {
        ...
    }
}
```

<!-- 
(Note: The real code gets the steps from Fitbit asynchronously using RxJava, but I did not put asynchronous code above so that it can be easily understood. )
 -->

---

Then... Last night, while reading Chapter 10 of  ["Growing Object-Oriented Software Guided by Tests"](https://www.bookdepository.com/book/9780321503626?a_aid=jflaga), I learned that someone (or sometwo :smile: ) has already named this kind of process before. 

Abelson & Sussman named it **_"programming by wishful thinking"_**.

> "... you write some code that uses a component, before you implement the component. This helps to discover what functions and data you need, and following this discovery will lead you to more simple and useful APIs." --- from ["Wishful Programming"](https://blog.thesoftwarecraft.com/2013/11/wishful-programming.html) post by Bart Bakker

This reminds me that there is nothing new under the sun. When [we do not read that much and] we think we discovered something new, we have to remember to assume that someone might already have discovered it before, and even formalized it or have already given it a name.

This also reminds me of one of the reasons why we need to read (or watch video lectures):

> "[The problems that we encounter today might have already been solved by someone else.](https://ryanholiday.net/how-to-read-more-a-lot-more/) We don't have to do everything by trial and error. We have to learn from the experiences of others." -- Ryan Holiday


(If you have comments about my English, and other things, please tell me : smile:)
