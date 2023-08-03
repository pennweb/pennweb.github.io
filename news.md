---
layout: page
title: News
permalink: /news/
api_url: https://penntoday.upenn.edu/api/news
---

Penn API provides JSON feeds for Penn Today news stories. Results are filtered by `school`, `topic`, `subtopic` or `president` by specifying taxonomy IDs.

### Topic

`https://penntoday.upenn.edu/api/news/topic/<id>`  

Returns items filtered by topic `<id>`.

Example: `https://penntoday.upenn.edu/api/news/topic/19` returns stories filtered by the topic "sports"


| Topic                               | id  |
|-------------------------------------|-----|
| Arts, Humanities, & Social Sciences |   1 |
| Sports                              |  19 |
| Campus & Community                  |   2 |
| Education, Business, & Law          |   4 |
| Health Sciences                     |   5 |
| Science & Technology                |   6 |


{% include subtopic.md %}

### School

`https://penntoday.upenn.edu/api/news/school/<id>`   

Returns items filtered by school.

Example: `https://penntoday.upenn.edu/api/news/school/83` returns stories filtered by the Wharton School

<div class="table-wrapper schools">
<table>
  <thead>
    <tr>
      <th>School</th>
      <th>ID</th>
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
      items = '';
      $.each(data, function(i, item) {
        name = "<td>" + item.name + "</td>";
        tid  = "<td>" + item.tid + "</td>";
        items += "<tr>" + name + tid + "</tr>";
      });
      $(".schools tbody").append(items);
  });
})(jQuery);
</script>

| School Name                             | ID  |
|-----------------------------------------|-----|
| Annenberg School for Communication      |  72 |
| Graduate School of Education            |  73 |
| Law School                              |  74 |
| Perelman School of Medicine             |  75 |
| School of Arts & Sciences               |  76 |
| School of Dental Medicine               |  77 |
| School of Design                        |  78 |
| School of Engineering & Applied Science |  79 |
| School of Nursing                       |  80 |
| School of Social Policy & Practice      |  81 |
| School of Veterinary Medicine           |  82 |
| Wharton School                          |  83 |


### President

`/api/news/president`  
  
Returns items related to the president.

