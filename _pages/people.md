---
permalink: /people/
title: "Researchers in Noah's ARK"
author_profile: true
---

<img src="../images/ARK-2022a.jpg">

<img src="../images/ARK-2022b.jpg">

Jump to:  <a href="#current">current members</a>, <a href="#phd">Ph.D. alumni</a>, <a href="#postdoc">postdoctoral alumni</a>, <a href="#masters">masters alumni</a>, and <a href="#other">other alumni</a>

<h3><a href="#current"></a>Current Members</h3>
<table style="border:0px;">
<colgroup>
       <col span="1" style="width: 40%;">
       <col span="1" style="width: 60%;">
    </colgroup>
{% for member in site.data.members %}
  <tr style="border:0px;"> <td style="border:0px;"> <a href="{{ member.url }}"><img style="display:block;" src="{{ member.image | prepend: "../images/" }}"></a></td><td style="border:0px;">
          <a href="{{ member.url }}">{{ member.name }}</a>, {{member.role}}</td>
  </tr>
{% endfor %}
</table>


<h3><a href="#phd"></a>Ph.D. Alumni</h3>
<table style="border:0px;">
<colgroup>
       <col span="1" style="width: 20%;">
       <col span="1" style="width: 80%;">
    </colgroup>
{% for member in site.data.phdalumni %}
  <tr style="border:0px;"> <td style="border:0px;"><a href="{{ member.url }}"><img style="display:block;" src="{{ member.image | prepend: "../images/" }}"></a></td><td style="border:0px;">
          <a href="{{ member.url }}">{{ member.name }}</a>, Ph.D. {{member.year}}, {{member.school}} (<i><a href="{{ member.thesisurl }}">{{ member.thesis }}</a></i>).  {{member.text}}</td>
  </tr>
{% endfor %}
</table>

<h3><a href="#postdoc"></a>Postdoctoral Alumni</h3>

<table style="border:0px;">
<colgroup>
       <col span="1" style="width: 20%;">
       <col span="1" style="width: 80%;">
    </colgroup>
{% for member in site.data.postdocalumni %}
<tr style="border:0px;"> <td style="border:0px;">
  {% assign image = member.image | strip_newlines %}
  {% if image == "" %}
  {% else %}
      <a href="{{ member.url }}"><img style="display:block;" src="{{ member.image | prepend: "../images/" }}"></a>
  {% endif %}
</td><td style="border:0px;">
<a href="{{ member.url }}">{{ member.name }}</a>, {{member.years}}, {{member.org}}.  Now: {{member.text}}.
</td> </tr>
{% endfor %}
</table>


<h3><a href="#masters"></a>Masters Alumni</h3>
<table style="border:0px;">
{% for member in site.data.mastersalumni %}
<tr style="border:0px;"> <td style="border:0px;">
{% assign url = member.url | strip_newlines %}
  {% if url == "" %}
  {{ member.name }}, M.S. {{member.year}}, {{member.school}}
  {% else %}
  <a href="{{ member.url }}">{{ member.name }}</a>, M.S. {{member.year}}, {{member.school}} 
  {% endif %}
 </td></tr>
{% endfor %}
</table>

<h3><a href="#other"></a>Other ARK Associates</h3>
Undergraduates, research programmers, visitors, etc. 
<table style="border:0px;">
{% for member in site.data.otheralumni %}
<tr style="border:0px;"> <td style="border:0px;">
  {% assign url = member.url | strip_newlines %}
  {% if url == "" %}
 	{{ member.name }} ({{member.type}}, {{member.years}})
  {% else %}
    <a href="{{ member.url }}">{{ member.name }}</a> ({{member.type}}, {{member.years}})
  {% endif %}
</td></tr>
{% endfor %}
</table>
