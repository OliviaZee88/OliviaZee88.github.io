---
layout: default
title: Tags
---
<section class="py-5">
    <div class="container">
        <h1 class="fw-bold mb-5 text-center">Tags</h1>
        
        <div class="mb-5 text-center">
            {% assign tags = site.tags | sort %}
            {% for tag in tags %}
            <a href="#{{ tag[0] | slugify }}" class="btn btn-outline-primary btn-sm m-1">{{ tag[0] }}</a>
            {% endfor %}
        </div>
        
        {% for tag in tags %}
        <div class="mb-5" id="{{ tag[0] | slugify }}">
            <h3 class="mb-3">{{ tag[0] }}</h3>
            <div class="list-group">
                {% for post in tag[1] %}
                <a href="{{ site.baseurl }}{{ post.url }}" class="list-group-item list-group-item-action d-flex justify-content-between align-items-center">
                    <div>
                        <h5 class="mb-1">{{ post.title }}</h5>
                        <small class="text-muted">
                            <i class="bi bi-calendar"></i> {{ post.date | date: "%B %d, %Y" }}
                        </small>
                    </div>
                    <span class="btn btn-sm btn-outline-primary">Read →</span>
                </a>
                {% endfor %}
            </div>
        </div>
        {% endfor %}
    </div>
</section>
