---
layout: page
title: Source Sheets
permalink: /source-sheets/
api_baseurl: /api/source-sheet?_format=json
api_url: https://penntoday.upenn.edu/api/source-sheet?_format=json
---

The Source Sheets API provides a JSON feed for Penn Today source sheets.

## URL

`{{ page.api_baseurl }}`
This base url returns Penn Today source sheets, most-recent first.
  
{% include json-response.md url=page.api_url %}

### Items

`items` is an array of JSON objects containing the source sheets data. Available fields are documented below. Each field is a `string` or `null`.

Key|Value
---|---
title|The source sheet title
body|The full source sheet body as it appears on Penn Today, including HTML
summary|The source sheet summary
date|The source sheet date in the format YYYY-MM-DD
url|The source sheet permalink

{% include json-items.md url=page.api_url %}

{% include json-page.md url=page.api_url %}
