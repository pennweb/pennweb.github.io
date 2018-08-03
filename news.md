---
layout: page
title: News
permalink: /news/
api_url: https://penntoday.upenn.edu/api/news?_format=json
---

The News API provides a JSON feed for Penn Today news stories. Results are filtered using the parameters described below, and pagination is provided for navigating the results.

## URL

`/api/news?_format=json`  

This base url returns the most recent news stories from Penn Today.
  
## URL Params

Results may be filtered by `school`, `topic`, `subtopic` or `president` using URL params. Specific pages of the result set are accessible with the `page` argument.

### President

`/api/news/president?_format=json`  
  
Returns items related to the president.

### School

`api/news/school/[id]?_format=json`   

Returns items filtered by school, where [id] is the school ID listed in the table below.

| School Name                             | ID  |
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

`Example: /api/news/school/83?_format=json` returns stories filtered by the Wharton School

### Topic

`api/news/topic/[id]?_format=json`  

Returns items filtered by topic, where [id] is a topic ID listed in the table below.


| Topic                               | id  |
|-------------------------------------|-----|
| Arts, Humanities, & Social Sciences |   1 |
| Sports                              |  19 |
| Campus & Community                  |   2 |
| Education, Business, & Law          |   4 |
| Health Sciences                     |   5 |
| Science & Technology                |   6 |

`Example: /api/news/topic/19?_format=json` returns stories filtered by the topic "sports"

{% include subtopic.md %}

### Page

The URL param `&page=[page_number]` added to the end of the URL returns a specific page of the result.

`Example: /api/news/topic/1?_format=json&page=10` returns the 10th page of news stories filtered by the topic "Arts & Humanities"

{% include json-response.md url=page.api_url %}

### Items

`items` is an array of JSON objects containing the news data. Available fields are documented below. Each field is a `string` or `null`.

Key|Value
---|---
title|The story title
body|The full story body as it appears on Penn Today, including HTML
summary|A summary of the story
date|The story date in the format `yyyy-mm-dd`
image|The full path to the story image, 600 x 400 pixels (3x2)
url|The story permalink

{% include json-items.md url=page.api_url %}

{% include json-page.md url=page.api_url %}

