---
layout: page
permalink: /publications/
title: publications
description: Find most PDFs by clicking on the DOI; otherwise, just send me an e-mail. Updated October 2018. 
years: [2018, 2017, 2016, 2015, 2014, 2013, 2012, 2011, 2010, 2009, 2008, 2007, 2006, 2005, 2004, 2003, 2002, 2001, 2000, 1999, 1998, 1997, 1996, 1993, 1992, 1991, 1988, 1985]
---

{% for y in page.years %}
  <h3 class="year">{{y}}</h3>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

