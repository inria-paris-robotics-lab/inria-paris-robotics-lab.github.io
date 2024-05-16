---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

Welcome to the Inria Paris Robotics Lab! Our platform hosts a diverse range of [robots]({{ 'Robots/' | relative_url }}) ([see here]({{ 'Robots/' | relative_url }})).

Our research spans across a wide range of fields from "classical robotics", with trajectory optimization, model predictive control, state estimation,... to computer vision or deep and reinforcement learning for end-to-end methods.

<img style="border-radius:10px;" src="{{ '/assets/imgs/RoboticsRoom.jpg' | absolute_url }}" alt="robotics room">

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