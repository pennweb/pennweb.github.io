---
layout: page
title: News
permalink: /news/
api_url: https://penntoday.upenn.edu/api/news
---

Penn API provides JSON feeds for Penn Today news stories. Results are filtered by `school`, `topic`, `subtopic` or `president` by specifying taxonomy IDs.

### Topic

`https://penntoday.upenn.edu/api/news/topic/<id>`

Example: `https://penntoday.upenn.edu/api/news/topic/19` returns stories filtered by the topic "sports"


| Topic                               | id  |
|-------------------------------------|-----|
| Arts, Humanities, & Social Sciences |   1 |
| Sports                              |  19 |
| Campus & Community                  |   2 |
| Education, Business, & Law          |   4 |
| Health Sciences                     |   5 |
| Science & Technology                |   6 |

{% include school.md %}

{% include subtopic.md %}


### President

`/api/news/president`  
  
Returns items related to the president.

