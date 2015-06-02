---
layout: page
title: Schedules
permalink: /schedules/
date: {{site.time | date: '%y'}}
---
<h2>{{site.time | date: '%Y-%m-%d' }} </h2>

{% assign data = site.data.schedules[schedule.data] %}
<body>
	{% include try.html %}
</body>