---
layout: page
title: Archive
# background: '/images/background/monika-sojcakova-S4sEHI2B0dU-unsplash.jpg'
background: '/images/background/aaron-burden-xG8IQMqMITM-unsplash.jpg'
sidebar_content: <iframe style="border-radius:12px" src="https://open.spotify.com/embed/playlist/1s3Rp82gIrYVnVSrSZQq71?utm_source=generator&theme=0" width="100%" height="352" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>
---

<!-- archive page code from http://chris.house/blog/building-a-simple-archive-page-with-jekyll -->

<div class="tags-expo">
    <div class="tags-expo-list">    
        <h5 class="badge badge-info">
            <a href="/blog/categories" class="post-tag text-light lead font-weight-bold">Categories</a>
        </h5>  
        <!-- 
        <h5 class="badge badge-info">
            <a href="/blog/tags" class="post-tag text-light lead font-weight-bold">Tags</a>
        </h5> 
        -->
    </div>
    <hr/>
    <div class="tags-expo-section">
        {% for post in site.posts %}
            {% unless post.categories contains 'Review' %}
                {% assign currentDate = post.date | date: "%B %Y" %}
                {% if currentDate != myDate %}
                    {% unless forloop.first %}</ul>{% endunless %}
                    <h2>{{ currentDate }}</h2>
                    <ul class="tags-expo-posts">
                    {% assign myDate = currentDate %}
                {% endif %}
                <li>
                    <small class="post-date">{{ post.date | date_to_string }} » </small>
                    <span>
                        <a class="post-title" href="{{ site.baseurl }}{{ post.url }}">
                            {{ post.title }}
                        </a>
                    </span>
                    <small class="badge badge-info">
                        {% assign category = post.categories[0] %}
                         <a class="post-tag text-light" 
                            href="{{ site.baseurl }}/blog/categories#{{ category }}">
                            {{ category }}
                        </a>
                    </small>
                </li>
                {% if forloop.last %}</ul>{% endif %}
            {% endunless %}
        {% endfor %}
    </div>
</div>

<!--
## [Want some _good_ and free books?](/free-books/)

## Old Blogs:

[jboyflaga2.blogspot.com](https://jboyflaga2.blogspot.com)

[jeremiahflaga.blogspot.com](https://jeremiahflaga.blogspot.com)
-->

## Old Blogs:

<div class="tags-expo">
    <div class="tags-expo-section">
        <ul class="tags-expo-posts">
            <li>
                <a href="https://jboyflaga2.blogspot.com">jboyflaga2.blogspot.com</a>
            </li>
            <li>
                <a href="https://jeremiahflaga.blogspot.com">jeremiahflaga.blogspot.com</a>
            </li>
        </ul>
    </div>
</div>

<!-- 
## [Want some _good_ and free books?](/free-books/)
 -->
