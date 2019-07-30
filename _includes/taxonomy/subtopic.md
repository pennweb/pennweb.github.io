#### Subtopic

<div class="table-wrapper taxonomy-subtopic">
<table>
  <thead>
    <tr>
      <th>Subject</th>
      <th>id</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
  </table>
</div>

<script>
(function($) {
  url = 'https://penntoday.upenn.edu/api/taxonomy/subtopic/all?_format=json';
  $.get(url, function(data) {
      //populate the table with taxonomy data
      taxonomy = '';
      $.each(data, function(i, item) {
        name = "<td>" + item.name + "</td>";
        tid  = "<td>" + item.tid + "</td>";
        taxonomy += "<tr>" + name + tid + "</tr>";
      });
      $(".taxonomy-subtopic tbody").append(taxonomy);
  });
})(jQuery);
</script>
