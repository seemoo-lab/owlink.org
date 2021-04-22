---
layout: page
title: Press
permalink: /press/
---

## PrivateDrop / AirDrop Contact Identifier Leakage

{% assign press = site.data.press["privatedrop"] | sort: "date" | reverse %}
{% for news in press %}
- [_{{ news.title }}_]({{ news.url }})  
  – **{{ news.paper }}**, {{ news.date | date_to_long_string }}
{% endfor %}


## Apple Find My / OpenHaystack / CVE-2020-9986

{% assign press = site.data.press["findmy"] | sort: "date" | reverse %}
{% for news in press %}
- [_{{ news.title }}_]({{ news.url }})  
  – **{{ news.paper }}**, {{ news.date | date_to_long_string }}
{% endfor %}
