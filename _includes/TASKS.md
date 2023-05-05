## Symbolic Expression
A symbolic expression $$\phi$$ is expressed as variables and constants connected by a set of operators. Variables are allowed to change across different contexts, while constants remain the same. Each operator has a predetermined arity, i.e., the number of operands taken by the operator. 
Each operand of an operator is either a variable, a constant, or a self-contained symbolic expression. 
A symbolic expression can also be drawn as a tree, where variables and constants reside in leaves, and operators reside in inner nodes. 

See [example expression](/file-formats/expression-format/).


## Classic Symbolic Regression
Given a dataset $$\mathcal{D}=[(\mathbf{x}_1, y_1), (\mathbf{x}_n,y_n)]$$ and a loss function $$\ell(\cdot,\cdot)$$, where  $$\mathbf{x}_i\in \mathbb{R}^m$$ and $$y_i\in \mathbb{R}$$, the objective of symbolic regression (SR) is to search for the optimal symbolic expression $$\phi^*$$ within the space of all candidate expressions $$\Pi$$, defined by a set of *mathematical functions*  (e.g., $$\exp, \ln,\sin,\cos$$) and *arithmetic operations* (e.g. $$+,-,\times,\div$$), that minimizes the average loss,
$$\phi^*=\arg\min_{\hat{\phi}\in \Pi}\frac{1}{n} \sum_{i=1}^n \ell(\hat{\phi}(\mathbf{x}_i), y_i)$$.


### Note
- We use `function_set` to denote the union of all the avaialble mathematical functions and arithmetic operations.

- The loss function $$\ell(\cdot,\cdot)$$ is defined at [this link](/data-query-protocol/#metric-functions).

## Our Scientist-in-the-loop Symbolic Regression
GIVEN:
- there are $$m$$ input variables, i.e., $$\mathbf{x}\in \mathbb{R}^m$$ and single output variable $$y\in \mathbb{R}$$.
- there are `function_set` that is a superset of mathematical operators for the true symbolic equation $$\phi$$.

Your task is to:
- query any data you want through our [data protocol](/data-query-protocol/). For example, you can query $$n$$ data points, $$\mathcal{D}=[(\mathbf{x}_1, y_1), (\mathbf{x}_n,y_n)]$$.
- Discover the optimal symbolic equation $$\hat{\phi}$$ by miminizimg the objective function ($$\ell$$):
$$\hat{\phi}^*=\arg\min_{\hat{\phi}\in \Pi}\frac{1}{n} \sum_{i=1}^n \ell(\hat{\phi}(\mathbf{x}_i), y_i)$$



## Execution of Your Learning algorithm
Here we show the main process on running the learning algorithm. For a complete black-box experiment, your algorithm will be executed from the command line as follow:
```bash
python main.py \
--input_eq_name PATH_TO_THE_INPUT_SYMBOLIC_EQUATION \
--noise_type uniform \ # noise type
--noise_scale 0.01 \ # noise rate
--output_filename ../PATH_TO_THE_OUTPUT_FILE \ # save your best predicted expressions into this file
```



### Input Arguments

- `--input_eq_name`: input equation file name. The format of "`PATH_TO_THE_INPUT_SYMBOLIC_EQUATION`" can be found at [Input file format](/file-formats/input-format/).
- `--noise_type`: type of noise that is applied over the output of true equation. See more noise types at [this link](data-query-protocol/#noise).
- `--noise_scale`: the sacle of noise.
- `--output_filename`: write the best predicted equation by your learning algoirthm. The format of "`PATH_TO_THE_OUTPUT_FILE`" can be found at [output file format](/file-formats/output-format/).



### Output of Program
Your program should writes the most possible equations predicted by the your learning algorithm to file `PATH_TO_THE_OUTPUT_FILE`, for the given input equation with name `PATH_TO_THE_INPUT_SYMBOLIC_EQUATION`.
