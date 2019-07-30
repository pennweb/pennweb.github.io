#### Penn Current

<div class="table-wrapper taxonomy-penn-current">
<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>ID</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
  </table>
</div>

<script>
(function($) {
  url = 'https://penntoday.upenn.edu/api/taxonomy/penn-current/all?_format=json';
  $.get(url, function(data) {
      //populate the table with taxonomy data
      taxonomy = '';
      $.each(data, function(i, item) {
        name = "<td>" + item.name + "</td>";
        tid  = "<td>" + item.tid + "</td>";
        taxonomy += "<tr>" + name + tid + "</tr>";
      });
      $(".taxonomy-penn-current tbody").append(taxonomy);
  });
})(jQuery);
</script>
