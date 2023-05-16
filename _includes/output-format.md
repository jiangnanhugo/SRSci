
## Output File Format

The output file must be
```python
YOUR_PREDICTED_EQUATION_IN_PREORDER_TRAVERSAL_FORMAT
```
It should the best symbolic expression discovered by the your algroithm.

## Example
```python
[('add','binary'), ('mul', 'binary'), ('0.1', 'const'), ('X_1', 'var'), ('sin', 'unary'), ('X_2', 'var')]
```
The above output is the preorder traversal of the expression "$0.1 * X_1 + \sin(X_2)$". See [Expression Format](/srsci/file-formats/expression-format/) for the defintion of expression.