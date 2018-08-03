### Subtopic

`api/news/subtopic/[id]?_format=json`  

Returns items filtered by subtopic, where [id] is a subtopic ID listed in the table below.

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
  url = 'https://penntoday.upenn.edu/api/taxonomy/subtopic?_format=json';
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
