
## Output File Format

The output file must be
```
algorithm_name: YOUR_ALGORITHM_NAME
equation_file_name: EXPRESSION_FILE_NAME.in
the_predicted_equation: YOUR_PREDICTED_EQUATION_IN_PREORDER_TRAVERSAL_FORMAT
```

### Example
```
algorithm_name: scibench_algorithm
equation_file_name: sample_equation.in
the_predicted_equation: "[('+','binary'), ('*', 'binary'), ('0.1', 'const'), ('X1', 'var'), ('sin', 'unary'), ('X2', 'var')]"
```
- This example says the user propose a learning algorithm for solving symbolic regression task with name `scibench_algorithm`. 
- The underlying true equation's filename is `sample_equation.in`. 
- The best symbolic expression discovered by the proposed algroithm is `"[('+','binary'), ('*', 'binary'), ('0.1', 'const'), ('X1', 'var'), ('sin', 'unary'), ('X2', 'var')]"`. See [Expression Format](/file-formats/expression-format/) for the defintion of expression.