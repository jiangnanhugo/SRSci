## Data Query Protocol

You are given the single file [symbolic_equation_evaluator_public.py](/assets/resources/symbolic_equation_evaluator_public.py).



Inside the **symbolic_equation_evaluator_public.py** file, there are a single class **Equation_evaluator**, which offers the following functions for the users.


## Initialization Function
```python
def __init__(self, equation_name, noise_type, noise_scale=0.1, metric_name='neg_nmse')
```
- `equation_name`: the datatype is `str`. It indicates the name of the equation.
- `noise_type`: the datatype is `str`. There are `['normal', 'exponential', 'uniform', 'laplace', 'logistic']` types of noise to be applied over the evaluated output `y`.
- `noise_scale`: the datatype is `float`. It means the scale of the noise to be applied.
- `metric_name`: the datatype is `str`. It will be used to compute the metric distance between the predicted output (`y_pred`) and the correct output (`y_true`). 
There are `['neg_mse', 'neg_rmse', 'neg_nmse', 'neg_nrmse', 'neglog_mse', 'inv_mse', 'inv_nmse',  'inv_nrmse', 'pearson', 'spearman', 'accuracy(r2)']` metrics available. See below for a detailed description.


## Data Query Function
```python
def evaluate(self, X)
```
### return
It evaluates the `y_true` from given input `X`. If the `noise_scale` is not set to `0`, it will return the **noisy** `y_true`.

### arguments
- `X`: The datatype is *numpy.Ndarray*. It is a matrix, where the first dimension corresponds to `batch_size` and the second dimension corresponds to `number_of_variables`. It represents the input to the symbolic expression.



## Loss Computation Functions
```python
def evaluate_loss(self, X, y_pred)
```

### return
The function will first computes the correct output (`y_true`) based on the input (`X`). Then the function returns a vector which is the loss between the correct (`y_true`) and predicted output (`y_pred`). Here the metric is pre-defined in `__init__` function via `metric-name`.

### arguments
- `X`: The datatype is *numpy.Ndarray*. It is a matrix, where the first dimension corresponds to `batch_size` and the second dimension corresponds to `number_of_variables`. It represents the input to the symbolic expression.
- `y_pred`: The datatype is *numpy.Ndarray*. It is a vector, where the first dimension is the batch_size. It represents the predicted output for the given input `X`.




```python
def evaluate_all_losses(self, X, y_pred)
```
### return
This function returns a dictionary of all the loss values. The keys in the dictionary are the metric names and the values in the dictionary are the corresponding loss value.


## Property Functions
```python
def get_eq_name(self)
```
It returns the equation name.

```python
def get_nvars(self)
```
It returns the number of variables in the true equations.

```python
def get_function_set(self)
```
It returns the `function_set` that is used to construct this equation.

## Metric Functions

- 'neg_mse': Negative mean squared error.
- 'neg_rmse':  Negative root mean squared error.
- 'neg_nmse': Negative normalized mean square error. 
- 'neg_nrmse': Negative normalized root mean squared error.
- 'neglog_mse': negative log mean squared error.
- 'inv_mse': inverse mean squared error. 
- 'inv_nmse': inverse normalized mean squared error. 
- 'inv_nrmse': inverse normalized root mean squared error.
- 'pearson':  Pearson correlation coefficient. 
- 'spearman': Spearman correlation coefficient.
- 'accuracy(r2)': Accuracy based on R2 value.


## Noise
- 'normal': [a normal (Gaussian) distribution](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.normal.html#numpy.random.Generator.normal).
- 'exponential': [an exponential distribution](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.exponential.html#numpy.random.Generator.exponential).
- 'uniform': [a uniform distribution](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.uniform.html#numpy.random.Generator.uniform).
- 'laplace': [the Laplace or double exponential distribution with specified location (or mean) and scale (decay)](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.laplace.html#numpy.random.Generator.laplace).
- 'logistic': [a logistic distribution](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.logistic.html#numpy.random.Generator.logistic).