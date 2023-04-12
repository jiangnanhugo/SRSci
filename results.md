---
title: Results
permalink: /results/
classes: wide
toc: false
---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<!-- <script src="vega-embed-6.15.0.min.js"></script> -->
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>


<script type="text/javascript">
    var view;

    fetch('../assets/plots/r2test.json')
      .then(res => res.json())
      .then(spec => render(spec, "#r2test"))
      .catch(err => console.error(err));
    fetch('../assets/plots/size.json')
      .then(res => res.json())
      .then(spec => render(spec, "#size"))
      .catch(err => console.error(err));
    fetch('../assets/plots/time.json')
      .then(res => res.json())
      .then(spec => render(spec, "#time"))
      .catch(err => console.error(err));
  vegaEmbed('#paretoR2Size', "../assets/plots/paretoR2Size.json").then(function(result) {
    // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);
  vegaEmbed('#paretoR2Time', "../assets/plots/paretoR2Time.json").then(function(result) {
    // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);
  vegaEmbed('#paretoTimeSize', ".../assets/plots/paretoTimeSize.json").then(function(result) {
    // Access the Vega view instance (https://vega.github.io/vega/docs/api/view/) as result.view
  }).catch(console.error);


    function render(spec, cont) {
      view = new vega.View(vega.parse(spec), {
        renderer:  'canvas',  // renderer (canvas or svg)
        container: cont,   // parent DOM container
        hover:     true       // enable hover processing
      });
      return view.runAsync();
    }
  </script>



Results are summarized over datasets. 

## Results for Black-box Regression

Select whether to analyze the results for every data set, Non-Friedman datasets, or Friedman datasets. You can also choose the aggregation function and the error measure.

### R2 score of the test set

<div id="r2test"></div>

<br><br>

### Size of the models

<div id="size"></div>

<br><br>

### Training time in seconds

<div id="time"></div>

<br><br>

### Accuracy-Complexity-Time Trade-offs

Considering the accuracy and simplicity of models simultaneously, this figure illustrates the trade-offs made by each method. 
Methods lower and to the left produce models with better trade-offs between accuracy and simplicity. 

<div id="paretoR2Size"></div>

<br><br>

<div id="paretoR2Time"></div>

<br><br>


<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<!-- <script src="vega-embed-6.15.0.min.js"></script> -->
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>


<script type="text/javascript">
    var view;

    fetch('../assets/plots/srGT.json')
      .then(res => res.json())
      .then(spec => render(spec, "#srGT"))
      .catch(err => console.error(err));
    fetch('../assets/plots/accGT.json')
      .then(res => res.json())
      .then(spec => render(spec, "#accGT"))
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

## Results for Ground-truth Problems

### Symbolically-verfied Solutions

How often a method finds a model symbolically equivalent to the ground-truth process

<div id="srGT"></div>

### Accuracy Solutions

How often a method finds a model with test set R^2>0.999

<div id="accGT"></div>

<br><br>
