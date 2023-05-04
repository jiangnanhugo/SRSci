Here we use an example symbolic equation `0.1 * X1 + sin(X2)`.
## Expression Tree
It is a specific kind of a binary tree used to represent expressions. 

### Example
```bash
      "+"
    /     \
  "*"     "sin"
  /  \      |
0.1  X1     X2    
```

## Pre-order Traversal
In a preorder traversal of a binary tree, we "visit" a node and then traverse both of its subtrees.

```python
["+", "*", "0.1", "X1", "sin","X2"]
```

## Extended Pre-order Traversal Format
The expression to be stored into file is based on the pre-order traversal. One thing left is to 
- differentiate unary and binary operators. For example `sine` function is a unary operator, that only takes one input. `+` is binary operator that needs two inputs. 
- differentiabe constants and vaiables in the leaves.

Therefore, we define the **extended** format based on the Pre-order Traversal.

### Example
```python
[("+",'binary'), ("*", "binary"), ("0.1", "const"), ("X1", "var"), ("sin", "unary"), ("X2", "var")]
```
It implies:
- "+", "*", "/" are binary operators;
- "sin" is a unary operator;
- "0.1" is a constant;
- "X1", "X2" are input variables.
