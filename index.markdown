---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---



<table>
<thead>
    <tr>
        <th colspan="2">Latest publications</th>
    </tr>
</thead>
<tbody>
{% for item in site.data.publications limit:3 %}
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
            <strong>{{ item.Publisher }}, {{ item.Year }}</strong>
        </td>
    </tr>
{% endfor %}
    <tr>
        <td></td>
        <td><a class="page-link" href="{{ '/publications.html' | relative_url }}">See more...</a>
        </td>
    </tr>
</tbody>
</table>