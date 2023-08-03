### School

`https://penntoday.upenn.edu/api/news/subtopic/<id>`  

Returns items filtered by subtopic `<id>`.

Example: `https://penntoday.upenn.edu/api/news/subtopic/266` returns stories filtered by the topic "Research"

<div class="table-wrapper subtopic">
<table>
  <thead>
    <tr>
      <th>Subtopic</th>
      <th>id</th>
    </tr>
  </thead>
  <tbody>
  </tbody>
  </table>
</div>

<script>
(function($) {
  url = 'https://penntoday.upenn.edu/api/taxonomy/schools/all?_format=json';
  $.get(url, function(data) {
      //populate the table with subtopic data
      subtopics = '';
      $.each(data, function(i, item) {
        name = "<td>" + item.name + "</td>";
        tid  = "<td>" + item.tid + "</td>";
        subtopics += "<tr>" + name + tid + "</tr>";
      });
      $(".subtopic tbody").append(subtopics);
  });
})(jQuery);
</script>
