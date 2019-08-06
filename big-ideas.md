---
layout: page
title: Big Ideas
permalink: /big-ideas/
api_url: https://penntoday.upenn.edu/api/big-ideas/all?_format=json
---

The News API provides a JSON feed for Penn Today news stories. Results are filtered using the parameters described below, and pagination is provided for navigating the results.

## URL

`/api/big-ideas/all?_format=json`  

This base url returns Big Ideas from Penn Today.

### Page

The URL param `&page=[page_number]` added to the end of the URL returns a specific page of the result.

`Example: /api/big-ideas/all?_format=json` returns the 10th page of Big Ideas results

{% include json-response.md url=page.api_url %}

### Items

`items` is an array of JSON objects containing the news data. Available fields are documented below. Each field is a `string` or `null`.

Key|Value
---|---
title|The Big Idea title
article_titles|An array of article titles under the parent Big Idea
article_nids|An array of article Node IDs under the parent Big Idea
nid|The node ID of the parent Big Idea

{% include json-items.md url=page.api_url %}

{% include json-page.md url=page.api_url %}

