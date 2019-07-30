---
layout: page
title: Taxonomy
permalink: /taxonomy/
---

The Taxonomy API provides a JSON feed of taxonomy term names IDs. This is useful in the scenario of first fetching a set of taxonomy IDs, and then using the IDs to filter another Penn API feed.

## URLS

Each Penn Today taxonomy has a unique url for fetching term data.

| Taxonomy          | API URL                                 |
|-------------------|-----------------------------------------|
|  Events           | /api/taxonomy/events                    |
|  Schools          | /api/taxonomy/schools                   |
|  Subject          | /api/taxonomy/subject                   |
| Subtopic          | /api/taxonomy/subtopic                  |
|  Article Mentions | /api/taxonomy/article-mentions          |
| Penn Current      | /api/taxonomy/penn-current              |
|  Penn Compact     | /api/taxonomy/penn-compact              |


Taxonomy results can be filtered by specifying one more taxonomy IDs from the tables below. Separate multiple taxonomies with the '+' operator. 

`Example: /api/taxonomy/subject/5?_format=json` returns the names and IDs of the Health Sciences term from the Subject taxonomy.

`Example: /api/taxonomy/subject/5+6?_format=json` returns the names and IDs of the Health Sciences and Science & Technology terms from the Subject taxonomy. 

{% include taxonomy/events.md %}

{% include taxonomy/subject.md %}

{% include taxonomy/subtopic.md %}

{% include taxonomy/schools.md %}

{% include taxonomy/article-mentions.md %}
{% include taxonomy/penn-compact.md %}

{% include taxonomy/penn-current.md %}


### Page

The URL param `&page=[page_number]` added to the end of the URL returns a specific page of the result.

`Example: /api/news/pitn/all?_format=json&page=10` returns the 10th page of news stories filtered by the topic "Arts & Humanities"

{% include json-response.md url=page.api_url %}

### Items

`items` is an array of JSON objects containing taxonomy term names and IDs. Available fields are documented below. Each field is a `string` or `null`.

Key|Value
---|---
name|The term name
tid |The term ID

{% include json-items.md url=page.api_url %}

{% include json-page.md url=page.api_url %}

