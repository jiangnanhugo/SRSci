
## Requirements
- Submit a zip file of your python package for symbolic regression using scientific approaches to [Easychair](https://easychair.org/cfp/content.cgi?a=30862459).

- Unzip the package will be a folder containing all the python files. Inside the folder, there should be a python program file called `main.py`. When we evaluate your program, we will execute the following command line argument:
```bash
python main.py --input_eq_name PATH_TO_THE_INPUT_SYMBOLIC_EQUATION \
--time_limit 3600
--output_filename ../PATH_TO_THE_OUTPUT_FILE \ # save your predicted expression into this file
```
Here, 
    - `input_eq_name` contains the file name storing the ground-truth equation and other information such as the type and amount of noise used during evaluation, etc. The ground-truth equation is used by the oracle to generate the output [will be discussed later]. The input file will be encrypted using a private key that only the organizers know, and the actual structure of the input file will not be released to prevent participants from directly reading the ground-truth equation. 

    - `time_limit` is used to let your program know the time limit of the evaluation. The unit is in seconds. Your program can design different strategies for competitions with different time limits. However, your program will be killed once the time limit has been reached, whether the program decides to quit itself or not.

    - `output_filename` designates the file you will need to write the symbolic equation you have found into.

## Data Oracle `Equation_evaluator`
- Your python package will need to access the oracle by calling the evaluate method from an object of the class `Equation_evaluator`. In your `main.py`, you will need to initialize an `Equation_evaluator` object. You can do this in the following way. First in the header of `main.py`:
```python
from symbolic_equation_evaluator import *
```
Then in the main program, execute:
```python
Eq_eval = Equation_evaluator(input_eq_name)
```
Where the `input_eq_name` denotes the input file name passed from the command line argument.


- `Equation_evaluator` provides you with this method:
```python
def evaluate(self, X)
```
This method can be used as the oracle. When queried by the input $X$, it returns noisy estimations of . Here, The datatype of $X$ is `numpy.ndarray`. It is a matrix. The first dimension corresponds to the batch size and the second dimension corresponds to `number_of_variables`. Basically, each row of $X$ represents one input to the symbolic expression. The output of evaluate will be a vector, where the $i$-th output is the noisy estimation of .

- Other useful functions of the Equation_evaluator class are:
```python
def get_nvars(self)
```
This function returns the number of input variables of the symbolic equation.
```python
def get_function_set(self)
```
This function returns the set of operators possibly used in the symbolic equation. An example output looks like:
```python
{'sin: 1, 'cos': 1, '+': 2, '-' : 2, '*' : 2, '/': 2, 'const': 0}
```
This output means the ground-truth equation may contain `add, sub, mul, div` as binary operators, `sin` and `cos` functions as unary operators and real-valued constants. The numbers as the values of the dictionary denote the arity of the operators. The full set of operators we consider are `[sin, cos, exp, log, pow, inv,add, sub, mul, div]`. Each competition track will use a subset of all operators.

## Output Requirements
- You will need to write the symbolic equation that you found into the output file. The output file contains only one line, the pre-order of the equation you have found. For example, the following line can be one valid equation in the output file:
```python
[('add','binary'), ('mul', 'binary'), ('0.1', 'const'), ('X_1', 'var'), ('sin', 'unary'), ('X_2', 'var')]
```
This represents the equation `0.1*X1 + sin(X2)`. You need to write `binary` behind all binary operators and `unary` behind all unary operators (there are only these two types). Constants need to be followed by a string const, and variables followed by a string var.
[\[Here is some explanation on what is the preorder traversal of an equation\]](/srsci/file-formats/expression-format/).

## Python Package Dependency
Your python package can depend on other packages available for installation via pip. [\[Here is a detailed example on specifying the extra packages\]](/srsci/competition-entry/requirements/#dependent-python-packages).

## Notice

- We give you `symbolic_equation_evaluator_public.py` and an example input file for you to debug your symbolic regressor. The content in the python and input files should be self-explanatory. `symbolic_equation_evaluator_public.py` is an example implementation of `symbolic_equation_evaluator.py` that we will use in the evaluation. However, the actual implementation of `symbolic_equation_evaluator.py` and the content in the input file will be different from the ones we provide to you, and the input file will be encrypted using keys only available to us. 


- **DO NOT TRY TO FIGURE OUT WAYS TO DECODE THE GROUNDTRUTH EQUATIONS BY STUDYING THESE EXAMPLE FILES.** 

- YOU SHOULD ONLY USE `get_nvars`, `get_function_set`, and `evaluate` from the `Equation_evaluator` object.
During the evaluation, we will first replace `the symbolic_equation_evaluator.py` in the zip folder with our own secret version. We will also manually check if your program calls methods other than the three suggested above. We will not include your submission in the evaluation if we find you use any side information other than that provided by the three methods.


