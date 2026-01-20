---
layout: page
title: Publications
permalink: /publications/
---

&rarr; Check out my [Google Scholar](https://scholar.google.com/citations?user=cuMq6bEAAAAJ).

<table>
{% for publi in site.data.publications %}
  <tr>
  <!-- <td>
    {% if publi.img %}
        <img src="/img/none.jpg">
    {% endif %}
  </td> -->
  <td>
    <div style="line-height: 1.2;">
    {% if publi.pdf %}
        <a href="/articles/{{ publi.pdf }}" target="_blank">{{ publi.title }}</a>
    {% else %}
        <a href="">{{ publi.title }}</a>
    {% endif %}
    <br>
    <span style="color: gray; font-size: 13px;">{{ publi.authors }}</span>
    {% if publi.journal %}
        <br>
        <span style="color: gray; font-size: 13px;">{{ publi.journal }}</span>
    {% endif %}
    {% if publi.conf %}
        <br>
        <span style="color: gray; font-size: 13px;">{{ publi.conf }}</span>
    {% endif %}
    {% if publi.workshop %}
        <br>
        <span style="color: gray; font-size: 13px;">{{ publi.workshop }}</span>
    {% endif %}
    <br>
    <span style="color: gray; font-size: 13px;">
        {% if publi.pdf %}
            [<a href="/articles/{{ publi.pdf }}" target="_blank">PDF</a>]
        {% endif %}
        {% if publi.supplem %}
            [<a href="/articles/{{ publi.supplem }}" target="_blank">Supplem</a>]
        {% endif %}
        {% if publi.website %}
            [<a href="{{ publi.website }}" target="_blank">Website</a>]
        {% endif %}
        {% if publi.github %}
            [<a href="{{ publi.github }}" target="_blank">Github</a>]
        {% endif %}
    </span>
    </div>
  </td>
  <td>
    <span style="font-size: 13px;">{{ publi.year }}</span>
  </td>
  </tr>
{% endfor %}
</table>