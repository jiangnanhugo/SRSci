## Evaluation Criteria


The final score of each competitor will be composed of:

- *acc*: Rank based on the accuracy (R^2) on a separate validation set for each data set.
- *simpl*: Rank based on the a simplicity (number of nodes calculating by traversing the sympy expression) of the model for each data set.

The rank will be calculated for each data set independently such that, with N participants, the k-th ranked competitor (k=1 being the best) will be assigned a value of *N - k + 1*. The final score will be the harmonic mean of all of the scores and each participant will be ranked accordingly:

```python
score = \frac{2*n}{ \sum_{i=1}^n (1/acc[i]) + (1/simpl[i]) for i in (1..n)]}
```

