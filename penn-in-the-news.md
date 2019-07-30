---
layout: page
title: Penn in the News
permalink: /penn-in-the-news/
api_url: https://penntoday.upenn.edu/api/penn-in-the-news?_format=json
---

The Penn in the News API provides a JSON feed for Penn Today "Penn in the News" items. Results are filtered using the "URL params" described below, and pagination is provided for navigating the results.

## URL

`/api/news/pitn/all?_format=json`  

This base url returns Penn in the News items from Penn Today.
  
## URL Params

Results may be filtered by `taxonomy`. Specific pages of the result set are accessible with the `page` argument.

### Taxonomy

Items can be filterd by Taxonomy by specifying one more taxonomy IDs from the tables below. Separate multiple taxonomies with the '+' operator. 

`Example: /api/news/pitn/5?_format=json` returns items from the Health Sciences subject.

`Example: /api/news/pitn/5+138?_format=json` returns items from the Health Sciences subject and Cancer Research subtopic. 


{% include taxonomy/subject.md %}

{% include taxonomy/subtopic.md %}

{% include taxonomy/schools.md %}

{% include taxonomy/penn-compact.md %}

### Page

The URL param `&page=[page_number]` added to the end of the URL returns a specific page of the result.

`Example: /api/news/pitn/all?_format=json&page=10` returns the 10th page of news stories filtered by the topic "Arts & Humanities"

{% include json-response.md url=page.api_url %}

### Items

`items` is an array of JSON objects containing the news data. Available fields are documented below. Each field is a `string` or `null`.

Key|Value
---|---
title|The story title
body|The Penn in the News body text as it appears on Penn Today, including HTML
date|The date of the Penn in the News item in the format `mm-dd-yyyy`
source|The Penn in the News item source, e.g. "The New Yorks Times", "Associated Press"
url|The URL of the story on the source's website.

{% include json-items.md url=page.api_url %}

{% include json-page.md url=page.api_url %}

