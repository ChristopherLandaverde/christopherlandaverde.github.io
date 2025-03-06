---
layout: default
title: Projects
permalink: /projects/
---

<h1>{{ page.title }}</h1>

<!-- Tabs -->
<ul class="tab-menu">
  <li><a href="#" class="tab-link active" data-tab="dashboards">Dashboards</a></li>
  <li><a href="#" class="tab-link" data-tab="python">Python</a></li>
  <li><a href="#" class="tab-link" data-tab="sql">SQL</a></li>
</ul>

<!-- Content for Each Category -->
<div class="tab-content active" id="dashboards">
  {% for project in site.pages %}
    {% if project.category == "dashboards" %}
      <article>
        <h2><a href="{{ project.url }}">{{ project.title }}</a></h2>
        <p>{{ project.description }}</p>
        {% if project.image %}
          <img src="{{ project.image }}" alt="{{ project.title }}" style="max-width: 100%;">
        {% endif %}
        <a href="{{ project.url }}">Read more...</a>
      </article>
      <hr>
    {% endif %}
  {% endfor %}
</div>

<div class="tab-content" id="python">
  {% for project in site.pages %}
    {% if project.category == "python" %}
      <article>
        <h2><a href="{{ project.url }}">{{ project.title }}</a></h2>
        <p>{{ project.description }}</p>
        {% if project.image %}
          <img src="{{ project.image }}" alt="{{ project.title }}" style="max-width: 100%;">
        {% endif %}
        <a href="{{ project.url }}">Read more...</a>
      </article>
      <hr>
    {% endif %}
  {% endfor %}
</div>

<div class="tab-content" id="sql">
  {% for project in site.pages %}
    {% if project.category == "sql" %}
      <article>
        <h2><a href="{{ project.url }}">{{ project.title }}</a></h2>
        <p>{{ project.description }}</p>
        {% if project.image %}
          <img src="{{ project.image }}" alt="{{ project.title }}" style="max-width: 100%;">
        {% endif %}
        <a href="{{ project.url }}">Read more...</a>
      </article>
      <hr>
    {% endif %}
  {% endfor %}
</div>

<!-- JavaScript for Tab Switching -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const links = document.querySelectorAll(".tab-link");
    const contents = document.querySelectorAll(".tab-content");

    links.forEach(link => {
      link.addEventListener("click", function(event) {
        event.preventDefault();
        const tab = this.getAttribute("data-tab");

        links.forEach(l => l.classList.remove("active"));
        this.classList.add("active");

        contents.forEach(content => {
          content.classList.remove("active");
          if (content.id === tab) {
            content.classList.add("active");
          }
        });
      });
    });
  });
</script>

<!-- CSS for Tabs -->
<style>

.tab-menu {
    margin-top: 30px; /* Adjust as needed */
}

.tab-menu {
    display: flex;
    list-style: none;
    padding: 0;
    gap: 12px; /* Adjust the gap for better spacing */
}




  .tab-menu li {
    margin-right: 20px;
  }

.tab-menu a {
    text-decoration: none;
    padding: 10px 16px; /* More padding inside buttons */
    background: #0073e6;
    color: white;
    border-radius: 5px;
}


  .tab-menu a.active {
    background: #004a99;
  }

  .tab-content {
    display: none;
    padding: 20px;
  }

  .tab-content.active {
    display: block;
  }
</style>

