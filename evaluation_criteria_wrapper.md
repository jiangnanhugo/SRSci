---
title: 
permalink: /results/evaluation-criteria/
toc: false
classes: wide
layout: single
---
<script>
MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']]
  }
};
</script>
<script id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
</script>

{% capture my_include %}{% include evaluation-criteria.md %}{% endcapture %}
{{ my_include | markdownify }}
