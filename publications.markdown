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
        <td> {% for robot in item.Robots %}{{ robot }} {% endfor %}</td>
        <td> <strong>{{ item.Title }}</strong>
             <br/>
             {{ item.Authors }}
             <br/>
             <strong>{{ item.Publisher }}, {{ item.Year }}</strong>
        </td>
    </tr>
{% endfor %}
</tbody>
</table>