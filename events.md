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
  
## URL Params

Results may be filtered by `category` using URL params. Specific pages of the result set are accessible with the `page` argument.


### Category

`api/events/category/[id]?_format=json`   

Returns items filtered by category, where [id] is the category ID listed in the table below.

|Category       | ID  |
|---------------|-----|
|Dance          |   8 |
|Exhibits       |   9 |
|Film           |  10 |
|Fitness        |  11 |
|For the Kids   |  12 |
|Music          |  13 |
|Readings       |  14 |
|Special Events |  15 |
|Sports         |  16 |
|Talks          |  17 |
|Theater        |  18 |


`Example: /api/events/category/17?_format=json` returns events filtered by Talks.

### Multiple Categories

Return items from multiple categories using the form 1+2+3.

`Example: /api/events/category/14+15+17?_format=json` returns events filtered by Readings, Special Events or Talks.

{% include json-response.md url=page.api_url %}

### ID

To fetch specific events by ID, specify the Node ID. Return multiple items by supplying multiple Node Ids.

`Example: /api/events/id/1+2+3?_format=json` returns 3 events with the Node IDs 1, 2 and 3.

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
