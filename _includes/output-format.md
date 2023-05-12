
## Output File Format

The output file must be
```python
YOUR_PREDICTED_EQUATION_IN_PREORDER_TRAVERSAL_FORMAT
```

### Example
```python
"[('+','binary'), ('*', 'binary'), ('0.1', 'const'), ('X1', 'var'), ('sin', 'unary'), ('X2', 'var')]"
```
- The best symbolic expression discovered by the proposed algroithm is `"[('+','binary'), ('*', 'binary'), ('0.1', 'const'), ('X1', 'var'), ('sin', 'unary'), ('X2', 'var')]"`. See [Expression Format](/file-formats/expression-format/) for the defintion of expression.