---
layout: page
title: News
permalink: /news/
api_url: https://penntoday.upenn.edu/api/news?_format=json
---

The News API provides a JSON feed for Penn Today news stories. Results are filtered using the parameters described below, and pagination is provided for navigating the results.

## URL

`/api/news?_format=json`  

This base url returns the most recent news stories from Penn Today.
  
## URL Params

Results may be filtered by `school`, `topic`, `subtopic` or `president` using URL params. Specific pages of the result set are accessible with the `page` argument.

### President

`/api/news/president?_format=json`  
  
Returns items related to the president.

### School

`api/news/school/[id]?_format=json`   

Returns items filtered by school, where [id] is the school ID listed in the table below.

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

`Example: /api/news/school/83?_format=json` returns stories filtered by the Wharton School

### Topic

`api/news/topic/[id]?_format=json`  

Returns items filtered by topic, where [id] is a topic ID listed in the table below.


| Topic                               | id  |
|-------------------------------------|-----|
| Arts, Humanities, & Social Sciences |   1 |
| Sports                              |  19 |
| Campus & Community                  |   2 |
| Education, Business, & Law          |   4 |
| Health Sciences                     |   5 |
| Science & Technology                |   6 |

`Example: /api/news/topic/19?_format=json` returns stories filtered by the topic "sports"

### Subtopic

`api/news/subtopic/[id]?_format=json`  

Returns items filtered by subtopic, where [id] is a subtopic ID listed in the table below.

| Subtopic                               | id  |
|----------------------------------------|-----|
| Admissions                             | 172 |
| Africana Studies                       | 165 |
| Alumni                                 | 110 |
| Anthropology                           |  86 |
| Archaeology                            |  87 |
| Art History                            |  88 |
| Astronomy                              | 145 |
| Awards                                 | 111 |
| Basketball                             | 104 |
| Behavioral Health                      | 136 |
| Big Data                               | 137 |
| Bioengineering                         | 169 |
| Biology                                | 146 |
| Business                               | 164 |
| Cancer Research                        | 138 |
| Chemical Engineering                   | 170 |
| Chemistry                              | 147 |
| Cinema & Media Studies                 |  89 |
| Climate Change                         | 148 |
| Commencement                           | 158 |
| Communications                         | 193 |
| Computer Science                       | 149 |
| Convocation                            | 159 |
| Criminology                            |  90 |
| Demography                             |  91 |
| Dental Medicine                        | 139 |
| Design                                 | 168 |
| Digital Humanities                     |  92 |
| Diversity                              | 112 |
| Earth and Environmental Science        | 188 |
| Earth Science                          | 150 |
| Economics                              |  93 |
| Education Policy                       | 128 |
| Energy Policy                          | 151 |
| English                                | 183 |
| Facilities and Real Estate             | 113 |
| Faculty                                | 114 |
| Financial Aid                          | 174 |
| First Generation Students              | 175 |
| Football                               | 105 |
| Gender, Sexuality, and Women's Studies | 166 |
| Geriatrics                             | 180 |
| Graduate Students                      | 178 |
| Health Care Policy                     | 140 |
| Hey Day                                | 160 |
| Historic Sporting Events               | 106 |
| History                                |  94 |
| Human Resources                        | 115 |
| Innovation                             | 129 |
| Internal medicine                      | 182 |
| International Relations                |  95 |
| Kelly Writers House                    | 190 |
| Law                                    | 130 |
| Libraries                              | 116 |
| Linguistics                            |  96 |
| Literature                             | 194 |
| Management                             | 131 |
| Marketing                              | 132 |
| Math                                   | 171 |
| Mechanical Engineering                 | 152 |
| Medical Ethics                         | 141 |
| Memorial Notices                       | 117 |
| Morris Arboretum                       | 187 |
| Music                                  | 192 |
| Nanotechnology                         | 153 |
| Neuroscience                           | 154 |
| Nursing                                | 142 |
| Penn Biden Center                      | 162 |
| Penn Compact                           | 118 |
| Penn Global                            | 119 |
| Penn Integrates Knowledge Professors   | 120 |
| Penn Recreation                        | 107 |
| Penn Relays                            | 109 |
| Penn Wharton China Center              | 163 |
| Performing Arts                        |  98 |
| Philosophy                             | 184 |
| Physics                                | 155 |
| Political Science                      |  99 |
| Positive Psychology                    | 100 |
| President                              | 121 |
| President's Engagement Prizes          | 185 |
| President's Innovation Prize           | 186 |
| Primary Education                      | 133 |
| Provost                                | 122 |
| Psychology                             | 101 |
| Public Health                          | 181 |
| Religious Studies                      | 102 |
| Robotics                               | 156 |
| Secondary Education                    | 134 |
| Silfen Forum                           | 161 |
| Social Work                            | 179 |
| Sociology                              | 167 |
| Staff                                  | 123 |
| Student Athletes                       | 108 |
| Sustainability                         | 125 |
| Teaching                               | 135 |
| Theatre Arts                           | 191 |
| Track & Field                          | 173 |
| Undergraduate Students                 | 177 |
| University Announcements               | 126 |
| Urban Planning                         | 189 |
| Veterinary Medicine                    | 143 |
| Visual Arts                            | 103 |
| Wellness                               | 144 |
| West Philadelphia                      | 127 |
| Wharton Business Radio                 | 176 |

`Example: /api/news/subtopic/138?_format=json` returns stories filtered by the subtopic "Cancer Research"

### Page

The URL param `&page=[page_number]` added to the end of the URL returns a specific page of the result.

`Example: /api/news/topic/1?_format=json&page=10` returns the 10th page of news stories filtered by the topic "Arts & Humanities"

{% include json-response.md url=page.api_url %}

### Items

`items` is an array of JSON objects containing the news data. Available fields are documented below. Each field is a `string` or `null`.

Key|Value
---|---
title|The story title
body|The full story body as it appears on Penn Today, including HTML
summary|A summary of the story
date|The story date in the format `yyyy-mm-dd`
image|The full path to the story image, 600 x 400 pixels (3x2)
url|The story permalink

{% include json-items.md url=page.api_url %}

{% include json-page.md url=page.api_url %}

