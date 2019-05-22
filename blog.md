---
layout: page
title: Blog
permalink: /blog/
---

<div class="posts">
    {% for post in site.posts %}
    {% if post.pinned %}
      <div class="lead alert">
        <i class="fas fa-thumbtack"></i> &nbsp; Pinned Post 
      </div>
      <div class="post">
        <h1 class="post-title">
          <a href="{{ site.baseurl }}{{ post.url }}">
            {{ post.title }}
          </a>
        </h1>
        <div class="hr"></div>
        <span class="post-date">{{ post.date | date_to_long_string }}</span>
          {{ post.content }}
      </div>
      <hr>
    {% endif %}
  {% endfor %}



  {% for post in paginator.posts %}
  <div class="post">
    <h1 class="post-title">
      <a href="{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>
    <span class="post-date">{{ post.date | date_to_string }}</span>
    {{ post.content }}
  </div>
  {% endfor %}
</div>

<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ site.baseurl }}{{ paginator.next_page_path }}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    <a class="pagination-item newer" href="{{ site.baseurl }}{{paginator.previous_page_path}}">Newer</a>
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div>