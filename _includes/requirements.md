
Here we collect all the requriements when evaluating your algorithms.
## Environmental Requirements


### Hardware Budget

The evaluations will be run on Linux machines with up to 8 CPU cores and 20 GB memory.

### Time Budget

Methods must adhere to a fixed time budget for the competition. 
*These time budgets are designed to be **generous**, not **restrictive***. 
Our goal is to allow "slow" implementations enough time to learn. 


The time limits are as follows:

- For datasets up to 3 variables, 30 minutes (0.5 hour)
- For datasets up to 10 variables, 180 minutes (3 hours)


## Submission Requirements
For the convenience of evaluting each of the algorithms, we need to enforce the following requirements about the directory so that we can sucessfully run your algorthm. 

1. You need to compress your code impelemntion into a **zip** file with **`YOUR_ALGOITHM_NAME.zip`**.

### Directory Requreiments

Inside your zip folder, the directory should contains **main.py** function, which is the default file to call your proposed algorithm. Here this the sample directory:
```bash
YOUR_ALGOITHM_NAME/
    main.py
     environment.yml
    EXTRA_FILES...
    ...
```

### Dependent Python Package requirements
In case you are using Python and your algorithm requires a specific version of Python and several packages with fixed versions. *If you do not need any extra packages, you are not required to provide this file.*

Inside your zip file, specify the extra packages and exact versions in **`environment.yml`**, which are required to be installed before running your algorithms.

#### Example `environment.yml` file

```yaml
name: YOUR_ALGOITHM_NAME

dependencies:
  - numpy=1.24.3
  - pandas=1.0
  - pip=20.0
  - python=3.8
```
this example specifies the python version to be `3.8` and also specifies to install `numpy`, `pandas` and `pip` packages with its coresponding version numbers. The name of this environment **must be** `YOUR_ALGOITHM_NAME`. We will install this specified python environment via the following command:
```
conda conda env create -f environment.yml
```
Then we will run the following command to swith to your specified python environment:
```
conda activate YOUR_ALGOITHM_NAME
```
See detailed disccusion of python environment at [this link](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).

### Input Arguments Requirements

4. Your `main.py` needs to takes the following input arguments:
```bash
--eq_name PATH_TO_THE_INPUT_SYMBOLIC_EQUATION \
--noise_type uniform \ # noise type
--noise_rate 0.01 \ # noise rate
--results ../PATH_TO_THE_OUTPUT_FILE.txt \ # save your best predicted expressions into this file
```
The format of `PATH_TO_THE_INPUT_SYMBOLIC_EQUATION` can be found at [Input file format]() and `PATH_TO_THE_OUTPUT_FILE.txt` is detailed in [Output file format]().






### Output Requirements