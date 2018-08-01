### Page

`page` is a JSON object containing pagination info, useful for navigating the result set.

Key|Value
---|---
current_page|An integer marking the current page number
total_items|Total number of items returned
total_pages|Total number of pages returned
items_per_page|Number of items per page

Example request using [jQuery.get()](https://api.jquery.com/jquery.get/)

{% highlight javascript %}

(function($) {
  url = '{{ include.url }}';
  $.get(url, function(data) {
    //pagination data is available in data.page
    totalItems = data.page.total_items;
    totalPages = data.page.total_pages;
  });
})(jQuery);

{% endhighlight javascript %}
