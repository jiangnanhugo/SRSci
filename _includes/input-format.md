The input expression file constains two lines. The first line contains a single integer, `0` indicates it is an Un-encrypted file and `1` indicates it is an encrypted file.

## Un-encrypted file format


### Example
```txt
0
b'{\n  "eq_name": "feynman-i.6.20",\n  "num_vars": 2,\n  "function_set": [\n    "exp",\n    "log",\n    "sqrt",\n    "add",\n    "sub",\n    "mul",\n    "div",\n    "inv",\n    "sin",\n    "cos",\n    "const"\n  ],\n  "eq_expression": "[('+','binary'), ('*', 'binary'), ('0.1', 'const'), ('X1', 'var'), ('sin', 'unary'), ('X2', 'var')]"\n}'
```
The second line represents a dictinary:
```python
{
    'eq_name': 'sample_equation', 
    'num_vars': 2, 
    'function_set': ['exp', 'log', 'sqrt', 'add', 'sub', 'mul', 'div', 'inv', 'sin', 'cos', 'const'], 
    'eq_expression': [('+','binary'), ('*', 'binary'), ('0.1', 'const'), ('X1', 'var'), ('sin', 'unary'), ('X2', 'var')]
}
```

## Encrypted file format


### Example
```txt
1
gAAAAABkTgSd8j6HB8Od-AXaD44-RgVbuxmIKZuSWpAvfcYYWOTkpUrMFuXxhtXjAHRlIrqRk0bjOfAHT-CdkfkyZzOPX17ky5uY0px-IIhlmAdIV8VXfOy-kiwvyxM7mqwRspxwHoIGOFY0g9cr-HF9-Ogmo0Z9hXipHdxDZYGdTUvkUVM-rDflVlJjTEH5Wgj6oL_yR4Vf5K_ZXwJJAfsaPFQEndESQw6MATjzJh7w9ChCDoDOhpPlyNZQTk2zfTlYtDJ4-KC2ghS_r2k1G1Rv44fNkRY4z4QVbc3qT1Av-qpMLqMOL8RVdwgEfGvXAswqJ2Pqk-nIn0fLomfRMOBNSYAJnHoIwA==
```
The second line represents the same dictionary as the above one, but a crypto function is used over the string.