
Here we collect all the requirements when evaluating your algorithms.
## Environmental Requirements


### Hardware Budget


|----------:|--------------:|
|    System | Ubuntu/CentOS |
| CPU cores |             8 |
|    Memory |        <=20GB |


### Time Budget

Methods must adhere to a fixed time budget for the competition. 
*These time budgets are designed to be **generous**, not **restrictive***. 
Our goal is to allow "slow" implementations have enough time to learn. 


|                |     Time |
|---------------:|---------:|
| <= 3 variables | 0.5 hour |
| <=10 variables |   3 hour |


## Submission Requirements
For the convenience of evaluating each of the algorithms, we need to enforce the following requirements about the directory so that we can successfully run your algorithm. 

### Compressed File
You need to compress your code impelemention into a **zip** file with **`YOUR_ALGORITHM_NAME.zip`**.

### Directory

Inside your zip folder, the directory should contain **main.py** function, which is the default file to call your proposed algorithm. Here this the sample directory:
```bash
YOUR_ALGORITHM_NAME.zip/
    main.py
    environment.yml
    EXTRA_FILES...
    ...
```

### Dependent Python Packages
In case you are using Python and your algorithm requires a specific version of Python and several packages with fixed versions. *If you do not need any extra packages, you are not required to provide this file.*

Inside your zip file, specify the extra packages and exact versions in **`environment.yml`**, which are required to be installed before running your algorithms.

Here is an example `environment.yml` file:
```yaml
name: YOUR_ALGORITHM_NAME

dependencies:
  - numpy=1.24.3
  - pandas=1.0
  - pip=20.0
  - python=3.8
```
this example specifies the Python version to be `3.8` and also specifies installing `numpy`, `pandas`, and `pip` packages with their corresponding version numbers. The name of this environment **must be** `YOUR_ALGOITHM_NAME`. We will install this specified Python environment via the following command:
```bash
conda env create -f environment.yml
```
Then we will run the following command to switch to your specified Python environment:
```bash
conda activate YOUR_ALGOITHM_NAME
```
See a detailed discussion of the Python environment at [this link](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).

<!-- ### Execution of Algorithm
You need to make sure your algorithm will be executed from the command line following [this example](), that is
- Your **`main.py`** accpets the required input arguments: `[--input_eq_name, --noise_type, --noise_scale, --output_filename]`.
- Your program output to the correct file and the output file format is also correct.
 -->
