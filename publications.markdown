---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Publications
---

| Robot | Publication |
|-------|-------------|
{% for item in site.data.publications %}| {{ item.Robot }} | **{{ item.Title }}**<br/>{{ item.Authors }}<br/>**{{ item.Publisher }}, {{ item.Year }}** |
{% endfor %}