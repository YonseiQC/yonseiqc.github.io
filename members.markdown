---
layout: splash 
title: Members
permalink: /members/
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/unsplash-image-1.jpg
---

<style>
.members-section { margin-bottom: 2.5em; }
.members-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5em;
  margin-top: 1em;
}
.member-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  width: 250px;
}
.member-photo {
  width: 130px;
  height: 130px;
  border-radius: 50%;
  object-fit: cover;
  background: #ddd;
  margin-bottom: 0.75em;
}
.member-name {
  font-weight: bold;
  font-size: 1em;
  margin: 0 0 0.2em;
}
.member-interests {
  font-size: 0.8em !important;
  color: #333;
  margin: 0.2em 0;
}
.member-links {
  margin-top: 0.4em;
  font-size: 0.85em;
}
.member-links a {
  margin: 0 0.25em;
}
.member-email {
  font-size: 0.75em;
}
</style>

{% assign role_order = "Professor,Postdoc,PhD Student,MS Student,Undergraduate" | split: "," %}

{% for role in role_order %}
  {% assign role_members = site.data.members | where: "role", role %}
  {% if role_members.size > 0 %}
<div class="members-section">
<h2>{{ role }}{% if role_members.size > 1 %}s{% endif %}</h2>
<div class="members-grid">
{% for member in role_members %}
  <div class="member-card">
    {% if member.photo and member.photo != "" %}
    <img src="{{ member.photo | relative_url }}" alt="{{ member.name }}" class="member-photo">
    {% else %}
    <img src="https://via.placeholder.com/130?text={{ member.name | split: ' ' | last | uri_escape }}" alt="{{ member.name }}" class="member-photo">
    {% endif %}
    <p class="member-name">{{ member.name }}</p>
    {% if member.interests and member.interests.size > 0 %}
    <p class="member-interests">{{ member.interests | join: " · " }}</p>
    {% endif %}
    <div class="member-links">
      {% if member.email and member.email != "" %}<a href="mailto:{{ member.email }}" class="member-email">{{member.email}}</a>{% endif %}
      {% if member.website and member.website != "" %}<a href="{{ member.website }}" target="_blank">Website</a>{% endif %}
      {% if member.github and member.github != "" %}<a href="https://github.com/{{ member.github }}" target="_blank">GitHub</a>{% endif %}
    </div>
  </div>
{% endfor %}
</div>
</div>
  {% endif %}
{% endfor %}
