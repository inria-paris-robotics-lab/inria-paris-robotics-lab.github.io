---
layout: default
title: Robots
---

# Our robots

{% for robot in site.data.robots %}
{% assign robot_name = robot[0] %}
{% assign robot_info = robot[1] %}
<div style="display:flex;margin:5%;border:solid black 1px;cursor: pointer;" onclick="location.href='/Robots/{{ robot_name }}.html';">
    <div style="width:50%;text-align: center;">
        <img src="{{robot_info.image_transparent}}" height="200px"/>
    </div>
    <div style="position:relative;width:50%">
        <h2>{{ robot_info.fullname }}</h2>

        <div style="position:absolute;bottom:0px;width:100%;">
            {% assign tag_list = robot_info.tag_list | split: ',' %}
            {% for tag in tag_list %} <code>{{ tag }}</code> {% endfor %}
        </div>
    </div>
</div>
{% endfor %}