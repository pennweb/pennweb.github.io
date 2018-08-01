---
layout: page
title: Events
permalink: /events/
api_url: https://penntoday.upenn.edu/api/events?_format=json
---

The Events API provides a JSON feed for upcoming Penn Today events.

## URL

`/api/events?_format=json`
This base url returns all upcoming events.
  
{% include json-response.md url=page.api_url %}


### Items

`items` is an array of JSON objects containing the event data. Available fields are documented below. Each field is a `string` or `null`.

Key|Value
---|---
title|The event title
body|The full event body as it appears on Penn Today, including HTML
summary|A summary of the event
location|The event location
start_date|The start date and time (EST) of the event in ISO format `yyyy-mm-ddThh:mm:ss`
end_date|The end date and time (EST) of the event in ISO format `yyyy-mm-ddThh:mm:ss`
event_url|An event-related link, typically outside of the penntoday.upenn.edu domain
image|The full path to the event thumbnail, 100 x 100 pixels
url|The event permalink

{% include json-items.md url=page.api_url %}

{% include json-page.md url=page.api_url %}
