### School

`https://penntoday.upenn.edu/api/news/school/<id>`

Example: `https://penntoday.upenn.edu/api/news/school/83` returns stories filtered by the Wharton School

<div class="table-wrapper schools">
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
  url = 'https://penntoday.upenn.edu/api/taxonomy/schools/all';
  $.get(url, function(data) {
      //populate the table with subtopic data
      subtopics = '';
      $.each(data, function(i, item) {
        name = "<td>" + item.name + "</td>";
        tid  = "<td>" + item.tid + "</td>";
        subtopics += "<tr>" + name + tid + "</tr>";
      });
      $(".schools tbody").append(subtopics);
  });
})(jQuery);
</script>
