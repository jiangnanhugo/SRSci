

## Task

We have provided a [conda environment](environment.yml), [configuration script](configure.sh) and [installation script](install.sh) that should make installation straightforward.
We've currently tested this on Ubuntu and CentOS. 
Steps:

1. Install the conda environment:



## 2. Reproducing the given example algorithm results
Here we show the main process on running the learning algorithm, evaluting the quality of the learned equations and submit the learning algorithm to the server for public and private leadboards.

After installing and configuring the conda environment, your learning algorithm should accept the following input arguments for a complete black-box experiment:

## Input Arguments Requirements
```bash
python gp.py \
-eq_name PATH_TO_THE_INPUT_SYMBOLIC_EQUATION \
-noise_type uniform \ # noise type
-noise_rate 0.01 \ # noise rate
-results ../PATH_TO_THE_OUTPUT_FILE.txt \ # save your best predicted expressions into this file
```
The format of `PATH_TO_THE_INPUT_SYMBOLIC_EQUATION` can be found at [Input file format]() and `PATH_TO_THE_OUTPUT_FILE.txt` is detailed in [Output file format]().

### Output
In the output file `PATH_TO_THE_OUTPUT_FILE.txt`, you will see 10 lines of symbolic regressions, that are identified as the most possible equations by the GP learning algorithms.

```txt
name_of_equation: xxxxxx.encrypt
name_of_your_algrithm: xxxxxxx
best_predicted_equations: 
```




### Output
next to each `path_to_result_file.txt` file, an additional file named `path_to_result_file.json` is saved with the symbolic assessment included. 



The definition of the output file format can be found at []().