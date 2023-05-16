## Loss Function 
Given the testing set $$\{\mathbf{X}_i,y_i\}_{i=1}^n$$ and the best predicted expression by the algorithm $\hat{f}(\cdot)$, here is the list of loss function that is going to be evluated:

- 'neg_mse': Negative mean squared error. The explicit form is: $-\frac{1}{n}\sum_{i=1}^n(y_{i}-\hat{f}(\mathbf{X}_{i}))^2$.
- 'neg_rmse':  Negative root mean squared error. The explicit form is: $-\sqrt{\frac{1}{n}\sum_{i=1}^n(y_{i}-\hat{f}(\mathbf{X}_{i}))^2}$.
- 'neg_nmse': Negative normalized mean square error. 
- 'neg_nrmse': Negative normalized root mean squared error.
- 'neglog_mse': negative log mean squared error.
- 'inv_mse': inverse mean squared error. The explicit form is: $\frac{1}{\frac{1}{n}\sum_{i=1}^n(y_{i}-\hat{f}(\mathbf{X}_{i}))^2}$.
- 'inv_nmse': inverse normalized mean squared error.  The explicit form is: $\frac{1}{\sqrt{\frac{1}{n}\sum_{i=1}^n(y_{i}-\hat{f}(\mathbf{X}_{i}))^2}}$.
- 'inv_nrmse': inverse normalized root mean squared error.
- 'pearson':  Pearson correlation coefficient. 
- 'spearman': Spearman correlation coefficient.
- 'accuracy(r2)': Accuracy based on R2 value.



## Noisy Evaluation
We also if the proposed method are robust subject to the noises. Let the scale of the noise is $\lambda$. The following list of noises are considered in the leader board:

- 'normal': [a normal (Gaussian) distribution](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.normal.html#numpy.random.Generator.normal).
- 'exponential': [an exponential distribution](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.exponential.html#numpy.random.Generator.exponential),  $\mathcal{N}(0, \lambda)$.
- 'uniform': [a uniform distribution](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.uniform.html#numpy.random.Generator.uniform).
- 'laplace': [the Laplace or double exponential distribution with specified location (or mean) and scale (decay)](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.laplace.html#numpy.random.Generator.laplace).
- 'logistic': [a logistic distribution](https://numpy.org/doc/stable/reference/random/generated/numpy.random.Generator.logistic.html#numpy.random.Generator.logistic).

<!-- ## Evaluation Scripts

After model training, the trained models are assessed for symbolic equivalence with the ground-truth data-generating processes. 
This is handled in [evaluate.py](evaluate.py). 

We will compare the following metrics of the predicted symbolic equations.

```bash
python evaluate.py \
-noise_type uniform \ # noise type
-noise_rate 0.01 \ # noise rate
-results ../path_to_result_file \ # save your Top-10 best predicted expressions into this file
``` -->