---
layout: page
title: News Feeds
permalink: /news/
api_url: https://penntoday.upenn.edu/api/news
---

Penn API provides JSON feeds for Penn Today news stories. 

1. News can be filtered by  `topic`, `subtopic`, `school` or `president`. Example: `https://penntoday.upenn.edu/api/news/topic/all` returns stories from all "topics".
2. Refine the filtering by providing one or more taxonomy IDs from the tables listed below. For example: `https://penntoday.upenn.edu/api/news/topic/19+2+5` returns stories from the "Topic" taxonomy, filtered by the topics "Sports", "Campus & Community", and "Health Sciences".


### Topic

`https://penntoday.upenn.edu/api/news/topic/<id>`

Example: `https://penntoday.upenn.edu/api/news/topic/19` returns stories filtered by the topic "sports"

Example: `https://penntoday.upenn.edu/api/news/topic/19+2+5` returns stories filtered by topics Sports, Campus & Community, and Health Sciences.

<!-- {% include taxonomy/subject.md %} -->

| Topic                               | ID  |
|-------------------------------------|-----|
| Arts, Humanities, & Social Sciences |   1 |
| Sports                              |  19 |
| Campus & Community                  |   2 |
| Education, Business, & Law          |   4 |
| Health Sciences                     |   5 |
| Science & Technology                |   6 |

### Subtopic

`https://penntoday.upenn.edu/api/news/subtopic/<id>`  

Example: `https://penntoday.upenn.edu/api/news/subtopic/266` returns stories filtered by the topic "Research"

{% include taxonomy/subtopic.md %}


### School

`https://penntoday.upenn.edu/api/news/school/<id>`

Example: `https://penntoday.upenn.edu/api/news/school/83` returns stories filtered by the Wharton School

<!-- {% include taxonomy/schools.md %} -->

| School                                  | ID  |
|-----------------------------------------|-----|
| Annenberg School for Communication      |  72 |
| Graduate School of Education            |  73 |
| Law School                              |  74 |
| Perelman School of Medicine             |  75 |
| School of Arts & Sciences               |  76 |
| School of Dental Medicine               |  77 |
| School of Design                        |  78 |
| School of Engineering & Applied Science |  79 |
| School of Nursing                       |  80 |
| School of Social Policy & Practice      |  81 |
| School of Veterinary Medicine           |  82 |
| Wharton School                          |  83 |


### President

`https://penntoday.upenn.edu/api/news/president`
  
Returns news related to the president.

