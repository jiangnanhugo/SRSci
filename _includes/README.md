
# SciBench: Scientist-in-the-loop benchmark for symbolic regression

We propose a new evaluation paradigm (**Scibench**) that simulates an integrated framework of scientist-in-the-loop for data generation and a learning algorithm for symbolic expression discovery.
The proposed benchmark standards solve a major gap in the existing benchmark evaluation: 
- the input data (experiment trials) is not necessarily generated from random *i.i.d.* distribution 
- the input data stays unchanged during learning.

Instead, from the history of experimental physics and  chemical element discovery, the data should be:
- actively queried throughout the process of scientific discovery. 

Specifically, our **Scibench** offers a unified data query protocol for the learning algorithms. Equipped with this extra flexibility, the learning algorithms can determine what training data is needed to uncover the underlying symbolic expression. 

# Benchmarked Methods

This benchmark currently consists of **14** symbolic regression methods, **7** other ML methods, including real-world and synthetic datasets from processes with and without ground-truth models.

Methods currently benchmarked:

- Age-Fitness Pareto Optimization (Schmidt and Lipson 2009) 
    [paper](https://dl.acm.org/doi/pdf/10.1145/1830483.1830584)
    , 
    [code](https://github.com/cavalab/ellyn)
- Age-Fitness Pareto Optimization with Co-evolved Fitness Predictors (Schmidt and Lipson 2009) 
    [paper](https://dl.acm.org/doi/pdf/10.1145/1830483.1830584?casa_token=8fAFUrPlfuUAAAAA:u0QJvX-cC8rPtdZri-Jd4ZxcnRSIF_Fu2Vn5n-oXVNu_i71J6ZECx28ucLPOLQY628drsEbg4aFvTw)
    , 
    [code](https://github.com/cavalab/ellyn)
- AIFeynman 2.0 (Udrescu et al. 2020)
    [paper](https://arxiv.org/abs/2006.10782)
    ,
    [code](https://github.com/SJ001/AI-Feynman)
- Bayesian Symbolic Regression (Jin et al. 2020)
    [paper](https://arxiv.org/abs/1910.08892)
    ,
    [code](https://github.com/ying531/MCMC-SymReg)
- Deep Symbolic Regression (Petersen et al. 2020)
    [paper](https://arxiv.org/pdf/1912.04871)
    , 
    [code](https://github.com/brendenpetersen/deep-symbolic-optimization)
- Fast Function Extraction (McConaghy 2011)
    [paper](http://trent.st/content/2011-GPTP-FFX-paper.pdf)
    ,
    [code](https://github.com/natekupp/ffx)
- Feature Engineering Automation Tool (La Cava et al. 2017)
    [paper](https://arxiv.org/abs/1807.00981)
    ,
    [code](https://github.com/lacava/feat)
- epsilon-Lexicase Selection (La Cava et al. 2016)
    [paper](https://arxiv.org/abs/1905.13266)
    ,
    [code](https://github.com/cavalab/ellyn)
- GP-based Gene-pool Optimal Mixing Evolutionary Algorithm (Virgolin et al. 2017)
    [paper](https://dl.acm.org/doi/pdf/10.1145/3071178.3071287?casa_token=CHa8EK_ic5gAAAAA:mOAOCu6CL-jHobGWKD2wco4NbpCyS-XTY5thb1dPPsyUkTkLHzmLMF41MWMGWLyFv1G8n-VFaqmXSw)
    ,
    [code](https://github.com/marcovirgolin/GP-GOMEA/)
- gplearn (Stephens)
    [code](https://github.com/trevorstephens/gplearn)
- Interaction-Transformation Evolutionary Algorithm (de Franca and Aldeia, 2020)
    [paper](https://www.mitpressjournals.org/doi/abs/10.1162/evco_a_00285)
    ,
    [code](https://github.com/folivetti/ITEA/)
- Multiple Regression GP (Arnaldo et al. 2014)
    [paper](https://dl.acm.org/doi/pdf/10.1145/2576768.2598291?casa_token=Oh2e7jDBgl0AAAAA:YmYJhFniOrU0yIhsqrHGzUN_60veH56tfwizre94uImDpYyp9RcadUyv_VZf8gH7v3uo5SxjjIPPUA)
    ,
    [code](https://github.com/flexgp/gp-learners)
- Operon (Burlacu et al. 2020)
    [paper](https://dl.acm.org/doi/pdf/10.1145/3377929.3398099?casa_token=HJgFp342K0sAAAAA:3Xbelm-5YjcIgjMvqLcyoTYdB0wNR0S4bYcQBGUiwOuwqbFfV6YnE8YKGINija_V6wCi6dahvQ3Pxg)
    ,
    [code](https://github.com/heal-research/operon)

- Semantic Backpropagation GP (Virgolin et al. 2019)
    [paper](https://dl.acm.org/doi/pdf/10.1145/3321707.3321758?casa_token=v43VobsGalkAAAAA:Vj8S9mHAv-H4tLm_GCL4DJdfW3e5SVUtD6J3gIQh0vrNzM3s6psjl-bwO2NMnxLN0thRJ561OZ0sQA)
    ,
    [code](https://github.com/marcovirgolin/GP-GOMEA)

Methods Staged for Benchmarking:

- PySR (Cranmer 2020)
    [code](https://github.com/MilesCranmer/PySR)
- PSTree (Zhang 2021)
    [code](https://github.com/hengzhe-zhang/PS-Tree)
    




# Contact
Yexiang Xue ([@xlnxyx](https://github.com/xlnxyx)), yexiang at purdue dot edu
Nan Jiang ([@jiangnanhugo](https://github.com/jiangnanhugo)), jiang631 at purdue dot edu

