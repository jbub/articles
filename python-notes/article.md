# Python notes

Some notes about things you can do in python.

## List comprehensions
```python
# generate matrix n x n
[[col for col in range(n)] for row in range(n)]

# flatten matrix
[num for row in m for num in row]

# generate identity matrix with the size of n
[[1 if col == row else 0 for row in range(n)] for col in range(n)]
```
