---
layout: page
title: Flashcards
permalink: /flashcards/
---
<div><button id="themeSelectorButton" onclick="toggleDropdown()">Select Theme</button>
<div id="themeDropdown" style="display:none"></div>
</div>
<ul>
{% for post in site.pages %}
    {% if post.layout == "flashcards" %}
        
        <li><a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
{% endfor %}
</ul>

<style>
    #themeSelectorButton {
        margin-bottom: 0px;
    }
    
    #themeDropdown {
        display: none;
        position: absolute;
        background-color: #f9f9f9;
        border: 1px solid #ccc;
        width: auto;
        z-index: 1;
    }
    #themeDropdown div {
        padding: 10px;
        cursor: pointer;
    }
    #themeDropdown div:hover {
        background-color: #ddd;
    }
</style>
<script>
    function toggleDropdown() {
        let dropdown = document.getElementById('themeDropdown');
        dropdown.style.display = dropdown.style.display === 'none' ? 'block' : 'none';
    }

    let pages = [];
    {% for post in site.pages %}
        {% if post.layout == "flashcards" %}
            pages.push({'title':'{{ post.title }}', 'url':'{{site.baseurl}}{{ post.url }}'});
        {% endif %}        
    {% endfor %}
    pages.forEach(page => {
        let option = document.createElement('div');
        option.innerText = page.title;
        option.dataset.url = page.url;
        option.addEventListener('click', function() {
            window.location.href = this.dataset.url;
        });
        document.getElementById('themeDropdown').appendChild(option);
    });
</script>



