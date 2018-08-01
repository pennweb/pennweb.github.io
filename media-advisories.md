---
layout: page
title: Media Advisories
permalink: /media-advisories/
api_baseurl: /api/media-advisories?_format=json
api_url: https://penntoday.upenn.edu/api/media-advisories?_format=json
---

The Media Advisories API provides a JSON feed for Penn Today media advisories.

## URL

`{{ page.api_baseurl }}`
This base url returns Penn Today media advisories, most-recent first.
  
{% include json-response.md url=page.api_url %}

### Items

`items` is an array of JSON objects containing media advisories data. Available fields are documented below. Each field is a `string` or `null`.

Key|Value
---|---
title|The advisory title
body|The full advisory body as it appears on Penn Today, including HTML
summary|A summary of the advisory
date|Advisory date in the format YYYY-MM-DD
url|Advisory permalink

{% include json-items.md url=page.api_url %}

{% include json-page.md url=page.api_url %}