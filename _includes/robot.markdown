# {{ include.fullname }} _(a.k.a {{ include.shortname }})_

{{ include.description }}

{% assign tag_list = include.tag_list | split: ',' %}
{% for item in tag_list %}
`{{ item }}`{% endfor %}