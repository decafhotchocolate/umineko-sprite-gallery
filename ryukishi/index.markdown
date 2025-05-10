---
layout: none
---
<style>
    body {
        background-color: #2F1817;
        color: #FFDE59;
    }

</style>

<div markdown="0" style="text-align: center;">
    <h1>Rokkenjima Yearbook 1986 (Ryukishi)</h1>
        <div id="container">
        {% assign counter = 0 %}
        {% assign row_open = false %}
        {% for image in site.static_files %}
            {% if image.path contains 'assets/images/ryukishi' %}
                {% if forloop.first or counter == 0 %}
                    <div class="row">
                    {% assign row_open = true %}
                {% endif %}
                <img src="{{ image.path }}" width=500 alt="">
                {% assign counter = counter | plus: 1 %}
                {% if counter == 3 %}
                    </div>
                    {% assign counter = 0 %}
                    {% assign row_open = false %}
                {% endif %}
            {% endif %}
        {% endfor %}
        {% if row_open %}
            </div>
        {% endif %}
        </div>
</div>