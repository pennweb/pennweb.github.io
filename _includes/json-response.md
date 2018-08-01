## JSON Response:
  
A successful response returns a JSON object with the keys `items` and `page`.

~~~~
{  
  "items" : []
  "page": {}
}
~~~~
Example request using [jQuery.get()](https://api.jquery.com/jquery.get/)
{% highlight javascript %}
(function($) {
  url = '{{ include.url }}';
  $.get(url, function(data) {
    //data contains data.items and data.page
    items = data.items;
    page = data.page;
  });
})(jQuery);
{% endhighlight javascript %}