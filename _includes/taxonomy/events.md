#### Events

<div class="table-wrapper events">
<table>
  <thead>
    <tr>
      <th>Event Category</th>
      <th>ID</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
  </table>
</div>

<script>
(function($) {
  url = 'https://penntoday.upenn.edu/api/taxonomy/events/all?_format=json';
  $.get(url, function(data) {
      //populate the table with taxonomy data
      taxonomy = '';
      $.each(data, function(i, item) {
        name = "<td>" + item.name + "</td>";
        tid  = "<td>" + item.tid + "</td>";
        taxonomy += "<tr>" + name + tid + "</tr>";
      });
      $(".events tbody").append(taxonomy);
  });
})(jQuery);
</script>
