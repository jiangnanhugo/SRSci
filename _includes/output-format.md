
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