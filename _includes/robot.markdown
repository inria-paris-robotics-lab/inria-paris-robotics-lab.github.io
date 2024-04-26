# {{ include.fullname }} _(a.k.a {{ include.shortname }})_

<!-- Parse the inputs -->
{% assign tag_list = include.tag_list | split: ',' %}
{% assign overview_list = include.overview_list | split: '--' %}
{% assign usage_list = include.usage_list | split: '--' %}

<div style="display: flex; flex-wrap: wrap; gap: 5%;">
    <div style="flex: 1 1 300px;">
        <img src="{{ include.image }}" alt="{{ include.image }}" style="object-fit: contain;">
    </div>
    <div style="flex: 1 1 300px;">
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

{{ include.description }}

{% for item in tag_list %}
`{{ item }}`{% endfor %}