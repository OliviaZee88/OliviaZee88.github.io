---
layout: default
title: All Posts
---
<section class="py-5">
    <div class="container">
        <h1 class="fw-bold mb-5 text-center">All Posts</h1>
        <div class="row justify-content-center">
            <div class="col-lg-8">
                <div class="list-group">
                    {% for post in site.posts %}
                    <a href="{{ site.baseurl }}{{ post.url }}" class="list-group-item list-group-item-action d-flex justify-content-between align-items-center">
                        <div>
                            <h5 class="mb-1">{{ post.title }}</h5>
                            <small class="text-muted">
                                <i class="bi bi-calendar"></i> {{ post.date | date: "%B %d, %Y" }}
                                {% if post.category %}
                                • <span class="badge bg-primary">{{ post.category }}</span>
                                {% endif %}
                            </small>
                        </div>
                        <span class="btn btn-sm btn-outline-primary">Read →</span>
                    </a>
                    {% endfor %}
                </div>
            </div>
        </div>
    </div>
</section>
