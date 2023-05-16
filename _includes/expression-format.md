Here we use an example symbolic expression "$0.1 * X_1 + \sin(X_2)$".
## Expression Tree
It is a specific kind of binary tree used to represent expressions. 

### Example
The expression "$0.1 * X_1 + \sin(X_2)$" can be represented as the following tree:
```bash
        'add'
      /       \
    'mul'      'sin'
   /   \         |
'0.1'  'X_1'   'X_2'    
```
Notice that the expression tree is not unique for the given symbolic expression. But gvien the expression tree, it can uniquely determine the symbolic expression.

## Pre-order Traversal
In a preorder traversal of a binary tree, we first *visit* a node,  then traverse its left subtrees, and finally its right subtrees.

Using the above expression tree, the pre-order traversal is:
```python
['add', 'mul', '0.1', 'X_1', 'sin','X_2']
```

## Extended Pre-order Traversal Format
The expression to be stored in the file is based on the pre-order traversal. We further need to:
- differentiate unary and binary operators for the internal nodes. For example `sine` function is a unary operator, that only takes one input. `+` is binary operator that needs two inputs. 
- differentiate constants and variables in the leaves.

Therefore, we define the **extended** format based on the Pre-order Traversal.

### Example
```python
[('add','binary'), ('mul', 'binary'), ('0.1', 'const'), ('X_1', 'var'), ('sin', 'unary'), ('X_2', 'var')]
```
It implies:
- 'add', 'mul' are binary operators, noted as 'binary';
- 'sin' is a unary operator, noted as 'unary';
- '0.1' is a constant, noted as 'const';
- 'X_1', 'X_2' are input variables, noted as 'var'.

Based on this list in *extended pre-order traversal format*, we can uniquely determine the expression tree and further uniquely determine its symbolic expression.
