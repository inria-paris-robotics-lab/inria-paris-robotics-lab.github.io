---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Publications
---

<table>
<thead>
    <tr>
        <th>Robots</th>
        <th>Publication</th>
    </tr>
</thead>
<tbody>
{% for item in site.data.publications %}
    <tr>
        <td>
        {% for robot in item.Robots %}
            {% assign robot_url = 'Robots/' | append: robot | append: '.html' | relative_url %}
            <a class="page-link" href="{{ robot_url }}">{{ robot }}</a>
        {% endfor %}
        </td>
        <td> <strong>{{ item.Title }}</strong>
             <br/>
             {{ item.Authors }}
             <br/>
             <em>{{ item.Publisher }}, {{ item.Year }}</em>
        </td>
    </tr>
{% endfor %}
</tbody>
</table>