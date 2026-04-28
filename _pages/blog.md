---
layout: default
permalink: /blog/
title: blog
description: Short research notes, tutorials, and explainers on Graph Machine Learning, Graph Neural Networks, missing features, and link prediction.
nav: true
nav_order: 3
pagination:
  enabled: true
  collection: posts
  permalink: /page/:num/
  per_page: 7
  sort_field: date
  sort_reverse: true
  trail:
    before: 1
    after: 3
---

<style>
  .blog-hero { padding: 2.5rem 0 1.25rem; }
  .blog-hero h1 {
    font-weight: 800;
    font-size: clamp(2.5rem, 6vw, 4.5rem);
    letter-spacing: -0.02em;
    line-height: 1;
    margin: 0 0 1.25rem;
    text-transform: uppercase;
  }
  .blog-hero .blog-intro {
    font-size: 1.05rem;
    color: var(--global-text-color-light, #555);
    max-width: 60ch;
    margin: 0;
  }

  .post-cards {
    list-style: none;
    padding: 0;
    margin: 2.5rem 0 0;
  }
  .post-cards > li { margin-bottom: 2rem; }

  .post-card {
    display: grid;
    grid-template-columns: minmax(240px, 38%) 1fr;
    gap: 2rem;
    align-items: center;
    padding: 1.75rem 1.75rem 1.75rem 1.5rem;
    border: 1px solid rgba(0,0,0,0.07);
    border-radius: 14px;
    background: var(--global-card-bg-color, #fff);
    box-shadow: 0 2px 12px rgba(15, 23, 42, 0.04);
    transition: box-shadow .2s ease, transform .2s ease;
  }
  .post-card:hover {
    box-shadow: 0 8px 28px rgba(15, 23, 42, 0.10);
    transform: translateY(-2px);
  }

  .post-card .thumb {
    width: 100%;
    aspect-ratio: 16 / 10;
    object-fit: contain;
    border-radius: 6px;
    background: #fafafa;
  }
  .post-card .thumb-placeholder {
    width: 100%;
    aspect-ratio: 16 / 10;
    border-radius: 6px;
    background: linear-gradient(135deg, #ecfdf5 0%, #d1fae5 100%);
    display: flex;
    align-items: center;
    justify-content: center;
    color: #047857;
    font-weight: 700;
    font-size: 1rem;
    letter-spacing: .04em;
    text-transform: uppercase;
  }

  .post-card .meta {
    display: flex;
    flex-wrap: wrap;
    gap: .35rem .75rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: .05em;
    font-size: .78rem;
    color: #15803d;
    margin-bottom: .65rem;
  }
  .post-card .meta a { color: inherit; text-decoration: none; }
  .post-card .meta .sep { color: #15803d; opacity: .55; }

  .post-card h2.post-title {
    font-weight: 800;
    font-size: clamp(1.35rem, 2.4vw, 1.85rem);
    line-height: 1.15;
    text-transform: uppercase;
    margin: 0 0 .9rem;
    color: #15803d;
    letter-spacing: -0.005em;
  }
  .post-card h2.post-title a {
    color: inherit;
    text-decoration: none;
    background-image: none;
  }
  .post-card h2.post-title a:hover { color: #166534; }

  .post-card .excerpt {
    color: var(--global-text-color, #1f2937);
    font-size: 1rem;
    line-height: 1.55;
    margin: 0 0 1.25rem;
  }

  .post-card .read-btn {
    display: inline-flex;
    align-items: center;
    gap: .5rem;
    padding: .6rem 1.2rem;
    border-radius: 999px;
    background: #2563eb;
    color: #fff;
    font-weight: 700;
    font-size: .92rem;
    text-decoration: none;
    transition: background .15s ease, transform .15s ease;
  }
  .post-card .read-btn:hover {
    background: #1d4ed8;
    transform: translateY(-1px);
    color: #fff;
    text-decoration: none;
  }
  .post-card .post-foot {
    margin-top: .85rem;
    font-size: .82rem;
    color: #6b7280;
  }

  /* dark mode adaptations */
  html[data-theme="dark"] .post-card {
    background: #1f2937;
    border-color: rgba(255,255,255,0.08);
  }
  html[data-theme="dark"] .post-card .meta,
  html[data-theme="dark"] .post-card h2.post-title { color: #4ade80; }
  html[data-theme="dark"] .post-card .meta .sep { color: #4ade80; opacity: .55; }
  html[data-theme="dark"] .post-card .excerpt { color: #e5e7eb; }
  html[data-theme="dark"] .post-card .post-foot { color: #9ca3af; }
  html[data-theme="dark"] .post-card .thumb { background: #111827; }

  @media (max-width: 640px) {
    .post-card {
      grid-template-columns: 1fr;
      gap: 1.25rem;
      padding: 1.25rem;
    }
  }
</style>

<div class="post">
  <header class="blog-hero">
    <h1>Blog Posts</h1>
    <p class="blog-intro">{{ page.description }}</p>
  </header>

  <ul class="post-cards">
    {%- assign posts = paginator.posts | default: site.posts -%}
    {% for post in posts %}

    {% if post.external_source == blank %}
      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
    {% else %}
      {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %}
    {% endif %}

    <li>
      <article class="post-card">
        <div>
          {% if post.thumbnail %}
            <img class="thumb"
                 src="{{ post.thumbnail | relative_url }}"
                 alt="{{ post.title | escape }}"
                 loading="lazy" />
          {% else %}
            {% assign initials = post.title | slice: 0, 1 %}
            <div class="thumb-placeholder">{{ initials }}</div>
          {% endif %}
        </div>

        <div>
          {% if post.tags and post.tags.size > 0 %}
            <div class="meta">
              {% for tag in post.tags limit: 3 %}
                <a href="{{ tag | prepend: '/blog/tag/' | relative_url }}">{{ tag | replace: '-', ' ' }}</a>
                {% unless forloop.last %}<span class="sep">·</span>{% endunless %}
              {% endfor %}
            </div>
          {% elsif post.categories and post.categories.size > 0 %}
            <div class="meta">
              {% for cat in post.categories limit: 3 %}
                <a href="{{ cat | prepend: '/blog/category/' | relative_url }}">{{ cat | replace: '-', ' ' }}</a>
                {% unless forloop.last %}<span class="sep">·</span>{% endunless %}
              {% endfor %}
            </div>
          {% endif %}

          <h2 class="post-title">
          {% if post.redirect == blank %}
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          {% elsif post.redirect contains '://' %}
            <a href="{{ post.redirect }}" target="_blank" rel="noopener">{{ post.title }}</a>
          {% else %}
            <a href="{{ post.redirect | relative_url }}">{{ post.title }}</a>
          {% endif %}
          </h2>

          {% if post.description %}
            <p class="excerpt">{{ post.description }}</p>
          {% endif %}

          {% if post.redirect == blank %}
            <a class="read-btn" href="{{ post.url | relative_url }}">Read the post →</a>
          {% elsif post.redirect contains '://' %}
            <a class="read-btn" href="{{ post.redirect }}" target="_blank" rel="noopener">Read the post →</a>
          {% else %}
            <a class="read-btn" href="{{ post.redirect | relative_url }}">Read the post →</a>
          {% endif %}

          <div class="post-foot">
            {{ post.date | date: '%B %d, %Y' }} &nbsp;·&nbsp; {{ read_time }} min read
            {% if post.external_source %}&nbsp;·&nbsp; {{ post.external_source }}{% endif %}
          </div>
        </div>
      </article>
    </li>

    {% endfor %}
  </ul>

  {% include pagination.html %}
</div>
