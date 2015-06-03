## Finally, I'm Done

It took me 5 days, but I've finally finished this blog. The main problem I ran into yesterday was trying to create my schedule page. I first tried to create a seperate category of posts under a folder called _categories in the _posts. I created an if statement in a schedules.md file for those pages, but it didn't. Then, I went to the Jekyll website for help where I got the idea to use the _data directory. I created a schedules.csv file with 4 field names, date(15-06-02), name (of task), time (ex. 10-11), and completed(y/n). I created a template in _includes. I spent 3 or more hours trying to create an if nested in a for loop that would list all of the items of "today's" date. which creates a schedule. I finally realized that for some reason, the if statement was either being ignored, or a string comparison of the date with (site.time | date: '%y-%m-%d' ) and the date from the csv file was not working. <a href = "http://stackoverflow.com/questions/24986305/iterate-over-a-list-of-posts-and-compare-the-date">This</a> answer to a post  helped a lot. I converted my date from the csv file into a variable, and then the if statement worked. I inclueded the try.html file into the schedule.md file, and my site was up and running. This is my final try.html file

```

{% assign Today = site.time | date: '%Y-%m-%d' %}
<ul>
{% for schedule in site.data.schedules %}
   {% if schedule.date == Today%}
   <li>
        <h3> {{ schedule.time }} {{ schedule.name }} {{ schedule.completed}} </h3>
	</li>
   {% endif %}   
{% endfor %}

</ul>

```