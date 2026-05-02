---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
You can also find my articles on <a href="{{ site.author.googlescholar }}" target="_blank">my Google Scholar profile</a>.
{% endif %}

{% include base_path %}

<div class="publications-wrapper">
  {% for post in site.publications reversed %}
    <div class="publication-item">
      {% if post.figure %}
      <div class="publication-figure">
        <img src="{{ post.figure }}" alt="{{ post.title | escape }}">
      </div>
      {% endif %}
      
      <div class="publication-details">
        <h3>
          <a href="{{ post.paperurl | default: post.url }}" target="_blank">
            {{ post.title }}
          </a>
        </h3>
        
        <div class="authors">
          {{ post.excerpt | markdownify | strip_html }}
        </div>
        
        <div class="venue">
          {{ post.venue }}
          {% if post.date %}
            , {{ post.date | date: "%Y" }}
          {% endif %}
          {% if post.code %}
            <a href="{{ post.code }}" target="_blank" title="Code on GitHub">
              <i class="fab fa-github"></i>
            </a>
          {% endif %}
          {% if post.pdf %}
            <a href="{{ post.pdf }}" target="_blank" title="PDF">
              <i class="fas fa-file-pdf"></i>
            </a>
          {% endif %}
        </div>
        
        {% if post.tldr %}
        <div class="tldr">
          <strong>TL;DR:</strong> {{ post.tldr }}
        </div>
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>
