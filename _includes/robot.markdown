<!-- Parse the inputs -->
{% assign robot_info = site.data.robots[include.robot] %}

<!-- Parse robot infos -->
{% assign tag_list = robot_info.tag_list | split: ',' %}
{% assign overview_list = robot_info.overview_list | split: '--' %}
{% assign usage_list = robot_info.usage_list | split: '--' %}
{% assign img_url = robot_info.image | relative_url %}

# {{ robot_info.fullname }}

<div style="display: flex; flex-wrap: wrap; gap: 5%; margin-top: 5%; margin-bottom: 5%">
    <div style="flex: 1 1 300px; align-self: center">
        <img src="{{ img_url }}" alt="{{ img_url }}" style="object-fit: contain;">
    </div>
    <div style="flex: 1 1 300px; align-self: center">
        <h3>Overview:</h3>
        <ul>
            {% for item in overview_list %}
            <li>{{ item }}</li>
            {% endfor %}
        </ul>
        <h3>Main usages:</h3>
        <ul>
            {% for item in usage_list %}
            <li>{{ item }}</li>
            {% endfor %}
        </ul>
    </div>
</div>

{{ robot_info.description }}

<table>
<thead>
    <tr>
        <th>Publications</th>
    </tr>
</thead>
<tbody>
{% for item in site.data.publications %}
    {% if item.Robots contains include.robot %}
        <tr>
            <td> <strong>{{ item.Title }}</strong>
                <br/>
                {{ item.Authors }}
                <br/>
                <em>{{ item.Publisher }}, {{ item.Year }}</em>
            </td>
        </tr>
    {% endif %}
{% endfor %}
</tbody>
</table>


{% for item in tag_list %}
`{{ item }}`{% endfor %}