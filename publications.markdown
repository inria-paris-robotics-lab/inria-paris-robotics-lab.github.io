---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Publications
---

| Robot | Publication |
|-------|-------------|
{% nolinebreaks %}
{% for item in site.data.publications %}
    | {% for robot in item.Robots %}{{ robot }}{% endfor %}
    | **{{ item.Title }}**<br/>{{ item.Authors }}<br/>**{{ item.Publisher }}, {{ item.Year }}** |
    {% endnolinebreaks %}
{% endfor %}