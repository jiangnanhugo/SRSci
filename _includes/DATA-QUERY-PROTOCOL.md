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




