---  
layout: page  
title: Conferences & Workshops  
permalink: /events/  
nav: true  
nav_order: 6  
---  
  
{% assign future_conferences = site.conferences | where_exp: "item", "item.date >= site.time" | sort: 'date' %}  
{% assign past_conferences = site.conferences | where_exp: "item", "item.date < site.time" | sort: 'date' | reverse %}  
  
## Upcoming Conferences  
  
{% for item in future_conferences %}  
  <div class="conference-item">  
    <h4>{{ item.title }}</h4>  
    <p><strong>Date:</strong> {{ item.date | date: "%B %d, %Y" }}</p>  
    <p><strong>Location:</strong> {{ item.location }}</p>  
    {{ item.content }}  
  </div>  
{% endfor %}  
  
## Past Conferences  
  
{% for item in past_conferences %}  
  <div class="conference-item">  
    <h4>{{ item.title }}</h4>  
    <p><strong>Date:</strong> {{ item.date | date: "%B %d, %Y" }}</p>  
    <p><strong>Location:</strong> {{ item.location }}</p>  
    {{ item.content }}  
  </div>  
{% endfor %}
