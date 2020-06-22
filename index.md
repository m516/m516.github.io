---
layout: default
title: Micah Mundy's Portfolio
---

## Personal Projects
* [CV Sandbox](https://m516.github.io/CV-Sandbox/) entails the work I've done with OpenCV for C++.

<div>
{% if site.data.pagelist.pagelist[0] %}
  {% for item in site.data.pagelist.pagelist %}
    <h3>{{ item.title }}</h3>
      {% if item.subfolderitems[0] %}
        <ul>
          {% for entry in item.subfolderitems %}
              <li><a href="{{ entry.url }}">{{ entry.page }}</a>
                {% if entry.subsubfolderitems[0] %}
                  <ul>
                  {% for subentry in entry.subsubfolderitems %}
                      <li><a href="{{ subentry.url }}">{{ subentry.page }}</a></li>
                  {% endfor %}
                  </ul>
                {% endif %}
              </li>
          {% endfor %}
        </ul>
      {% endif %}
    {% endfor %}
{% endif %}
</div>

