Example request using [jQuery.get()](https://api.jquery.com/jquery.get/) 

{% highlight javascript %}
(function($) {
  url = '{{ include.url }}';
  $.get(url, function(data) {
    $.each(data.items, function(i, item) {
      //fields are available as item.title, item.body, etc. 
    });
  });
})(jQuery);
{% endhighlight javascript %}
