# {{ include.fullname }}

<!-- Parse the inputs -->
{% assign tag_list = include.tag_list | split: ',' %}
{% assign overview_list = include.overview_list | split: '--' %}
{% assign usage_list = include.usage_list | split: '--' %}

<div style="display: flex; flex-wrap: wrap; gap: 5%; margin-top: 5%; margin-bottom: 5%">
    <div style="flex: 1 1 300px; align-self: center">
        <img src="{{ include.image }}" alt="{{ include.image }}" style="object-fit: contain;">
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

{{ include.description }}

| Publications |
|--------------|
{% nolinebreaks %}
{% for item in site.data.publications %}
{% if item.Robots contains include.shortname %}
| **{{ item.Title }}**<br/>{{ item.Authors }}<br/>**{{ item.Publisher }}, {{ item.Year }}** |
\break
{% endif %}
{% endfor %}
{% endnolinebreaks %}


{% for item in tag_list %}
`{{ item }}`{% endfor %}