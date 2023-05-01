---
title: Datasets
permalink: /encrypted_equations/
toc: false
---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<!-- <script src="vega-embed-6.15.0.min.js"></script> -->
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>


<script type="text/javascript">
    var view;

    fetch('../assets/plots/datasets.json')
      .then(res => res.json())
      .then(spec => render(spec, "#view"))
      .catch(err => console.error(err));


    function render(spec, cont) {
      view = new vega.View(vega.parse(spec), {
        renderer:  'canvas',  // renderer (canvas or svg)
        container: cont,   // parent DOM container
        hover:     true       // enable hover processing
      });
      return view.runAsync();
    }
  </script>

<div id="view"></div>
(click on legend name to select the points, shift+click to select both groups.)



**Ground-truth Regression Problems**: problems for which the ground-truth model known. 
Includes datasets from the [Feynman Symbolic Regression Database](https://space.mit.edu/home/tegmark/aifeynman.html) and dynamical systems from the [ODE-Strogatz Database](https://lacava.github.io/ode-strogatz/). 
130 total. 

<br><br>
