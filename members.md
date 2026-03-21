---
layout: page
title: Members
lead: People in the OdenseNLP research group. Add or edit members in the `_members/` collection.
permalink: /members/
wide: true
---

{% assign sorted_members = site.members | sort: "order" %}

<section class="member-grid" aria-label="Research group members">
  {% for member in sorted_members %}
    <article class="member-card">
      <img src="{{ member.image | default: '/assets/images/members/member-placeholder.svg' | relative_url }}" alt="Portrait of {{ member.name }}" />
      <div class="member-content">
        <h3><a href="{{ member.url | relative_url }}">{{ member.name }}</a></h3>
        <p class="meta">{{ member.role }}</p>
        <p>{{ member.excerpt | strip_html | truncate: 135 }}</p>
        {% include member-links.html person=member %}
        {% if member.research_areas and member.research_areas.size > 0 %}
          <div class="tag-row">
            {% for area in member.research_areas %}
              <span class="tag">{{ area }}</span>
            {% endfor %}
          </div>
        {% endif %}
      </div>
    </article>
  {% endfor %}
</section>
