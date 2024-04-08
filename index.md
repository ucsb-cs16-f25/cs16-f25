---
layout: page
title: GS Assignments
nav_order: 1
description: Lab Assignments
---

# GradeScope Programming Assignments

This is the website for Gradescope Programming Assignments, you will find all lab instructions
in the navbar on the left once they are released.

For more information about this course, please go to our canvas page:
[https://ucsb.instructure.com/courses/19503](https://ucsb.instructure.com/courses/19503)


{% for lab in site.labs %}
* [{{lab.num}}]({{ lab.url | relative_url}})&mdash;{{lab.desc}}
{% endfor %}

# Formatting guide

<a href="assets/pdfs/formatting-guide.pdf" target="_blank">Open in new tab</a>

<embed src="assets/pdfs/formatting-guide.pdf" width="800" height="500"> 
