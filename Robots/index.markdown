---
layout: default
title: Robots
---

# Our robots

{% for robot in site.data.robots %}
{% assign robot_name = robot[0] %}
{% assign robot_info = robot[1] %}
<div class="robot-card" onclick="location.href='/Robots/{{ robot_name }}.html';">
    <div class="robot-img">
        <img src="{{robot_info.image_transparent}}" height="200px"/>
    </div>
    <div class="robot-description">
        <h2>{{ robot_info.fullname }}</h2>

        <div class="tag-list">
            {% assign tag_list = robot_info.tag_list | split: ',' %}
            {% for tag in tag_list %} <code>{{ tag }}</code> {% endfor %}
        </div>
    </div>
</div>
{% endfor %}

<style>
.robot-card {
    display:flex;
    margin:5%;
    border:solid rgba(0, 0, 0, 0) 1px;
    box-shadow: 0px 5px 10px 0px rgba(0, 0, 0, 0.5);
    border-radius: 10px;
    cursor: pointer;
}

.robot-img {
    width:50%;
    height:auto;
    text-align: center;
}

.robot-description {
    position:relative;
    width:50%;

}

.robot-card:hover {
    opacity: 75%;

    /* Extra transparency for some elements */
    border: 1px solid rgba(0, 0, 0, .75);
    .robot-img {
        opacity:75%;
    }
}

.tag-list {
    text-align: center;
    position:absolute;
    bottom:0px;
    width:100%;
  }

.tag-list code {
    white-space: nowrap;
    overflow: auto;
    display: inline-block;
}

@media screen and (max-width: 600px) {
    .robot-card {
        flex-direction: column;
        div {
            width: 90%;
            margin:auto;
        }
    }
    .robot-description {
        text-align: center;
    }
    .tag-list {
        position:relative;
    }
}
</style>