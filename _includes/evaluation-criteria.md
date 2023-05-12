## Evaluation Criteria

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


## Evaluation Scripts

After model training, the trained models are assessed for symbolic equivalence with the ground-truth data-generating processes. 
This is handled in [evaluate.py](evaluate.py). 

We will compare the following metrics of the predicted symbolic equations.

```bash
python evaluate.py \
-noise_type uniform \ # noise type
-noise_rate 0.01 \ # noise rate
-results ../path_to_result_file \ # save your Top-10 best predicted expressions into this file
```