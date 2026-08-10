---
layout: base
lang: en
title: About DeepLang
description: About the DeepLang programming language
---
{% assign t = site.data[page.lang] %}
{% assign a = t.about_page %}

<!-- Hero -->
<section class="about-hero">
    <div class="about-hero-inner">
        <h1>{{ a.title }}</h1>
        <p class="about-hero-sub">{{ a.subtitle }}</p>
    </div>
</section>

<!-- Mission -->
<section class="section">
    <div class="section-inner">
        <div class="about-mission">
            <h2>{{ a.mission.title }}</h2>
            <p>{{ a.mission.text }}</p>
        </div>
    </div>
</section>

<!-- Timeline -->
<section class="section section-alt">
    <div class="section-inner">
        <h2 class="about-section-title">{{ a.timeline.title }}</h2>
        <div class="timeline">
            {% for item in a.timeline.items %}
            <div class="timeline-item">
                <div class="timeline-marker">
                    <span class="timeline-year">{{ item.year }}</span>
                </div>
                <div class="timeline-body">
                    <h3>{{ item.title }}</h3>
                    <p>{{ item.desc }}</p>
                </div>
            </div>
            {% endfor %}
        </div>
    </div>
</section>

<!-- Repositories -->
<section class="section">
    <div class="section-inner">
        <h2 class="about-section-title">{{ a.repos.title }}</h2>
        <div class="about-repos">
            {% for repo in a.repos.items %}
            <a href="https://github.com/deeplang-org/{{ repo.name }}" class="about-repo-card" target="_blank" rel="noopener">
                <span class="about-repo-icon">{{ repo.icon }}</span>
                <div>
                    <h3>{{ repo.name }}</h3>
                    <p>{{ repo.desc }}</p>
                </div>
                <span class="about-repo-arrow">→</span>
            </a>
            {% endfor %}
        </div>
    </div>
</section>

<!-- Contact -->
<section class="section section-alt">
    <div class="section-inner">
        <h2 class="about-section-title">{{ a.contact.title }}</h2>
        <p class="about-contact-intro">{{ a.contact.text }}</p>
        <div class="about-contacts">
            {% for person in a.contact.items %}
            <a href="mailto:{{ person.mail }}" class="about-contact-card">
                <span class="contact-avatar">{{ person.label | slice: 0 }}</span>
                <div>
                    <span class="contact-name">{{ person.label }}</span>
                    <span class="contact-mail">{{ person.mail }}</span>
                </div>
            </a>
            {% endfor %}
        </div>
    </div>
</section>
