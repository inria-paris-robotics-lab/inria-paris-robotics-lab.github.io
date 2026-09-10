---
layout: default
title: Robots
---

# Our robots

<div class="card" onclick="location.href='/Robots/Current/index.html';">
    <h1>Robots currently in use</h1>
</div>

<div class="card" onclick="location.href='/Robots/Retired/index.html';">
    <h1>Robots retired</h1>
</div>

<style>

.card {

    margin:5%;
    border:solid rgba(0, 0, 0, 0) 1px;
    box-shadow: 0px 5px 10px 0px rgba(0, 0, 0, 0.5);
    border-radius: 10px; 
    cursor: pointer;
    vertical-align: middle;
    text-align: center;
    line-height: 90px; 
}

.card:hover {
    opacity: 75%;

    /* Extra transparency for some elements */
    border: 1px solid rgba(0, 0, 0, .75);
    .robot-img {
        opacity:75%;
    }
}

@media screen and (max-width: 600px) {
    .card {
        flex-direction: row;
        div {
            width: 90%;
            margin:auto;
        }
    }
}
</style>