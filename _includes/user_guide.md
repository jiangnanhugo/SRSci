# User Guide

## 1. Installation

We have provided a [conda environment](environment.yml), [configuration script](configure.sh) and [installation script](install.sh) that should make installation straightforward.
We've currently tested this on Ubuntu and CentOS. 
Steps:

1. Install the conda environment:

```bash
conda env create -f environment.yml
conda activate scibench
```

2. Install the given package:

```bash
cd scibench
python setup.py install
```


## 2. Reproducing the given example algorithm results
Here we show the main process on running the learning algorithm, evaluting the quality of the learned equations and submit the learning algorithm to the server for public and private leadboards.

After installing and configuring the conda environment, your learning algorithm should accept the following input arguments for a complete black-box experiment:

```bash
python gp.py \
-noise_type uniform \ # noise type
-noise_rate 0.01 \ # noise rate
-results ../path_to_result_file.csv \ # save your Top-10 best predicted expressions into this file
-time_limit 3600  \ # the total running time of the whole program.
```

### Output
In the output file `path_to_result_file.csv`, you will see 10 lines of symbolic regressions, that are identified as the most possible equations by the GP learning algorithms.





## 3. Evaluation

After model training, the trained models are assessed for symbolic equivalence with the ground-truth data-generating processes. 
This is handled in [evaluate.py](evaluate.py). 

We will compare the following metrics of the predicted symbolic equations.

```bash
python evaluate.py \
-noise_type uniform \ # noise type
-noise_rate 0.01 \ # noise rate
-results ../path_to_result_file \ # save your Top-10 best predicted expressions into this file
```

### Output
next to each `path_to_result_file.csv` file, an additional file named `path_to_result_file.json` is saved with the symbolic assessment included. 

## 4. Submission

For the convenience of evaluting each of the algorithms, we need to enforce the following requirements about the directory so that we can sucessfully run your algorthm. 

1. you need to compress your code impelemntion into a **zip** file.

2. Specify the extra packages and exact versions in **requirements.txt**, which are required to be installed before running your algorithms.

2. In side your zip folder, the directory should contains **main.py** function, which is the default file to call your proposed algorithm.

```bash
YOUR_ALGOITHM/
    main.py
    requirements.txt
    extra_files....
```


