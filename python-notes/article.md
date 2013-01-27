# Python notes

Some notes about things you can do in python.

## List comprehensions

List comprehensions provide a concise way to create lists.

```python
# generate matrix n x n
[[col for col in range(n)] for row in range(n)]

# flatten matrix
[num for row in m for num in row]

# generate identity matrix with the size of n
[[1 if col == row else 0 for row in range(n)] for col in range(n)]
```

## Sets

Sets are unordered collections of unique elements.

```python
# lists with duplicate items
a = [1, 2, 3, 45, 6, 8, 8, 9, 3, 3]
b = [7, 8, 9, 4, 5, 1, 2, 4, 5, 6]

# notice that there are only unique items in the sets
sa = set(a) # set([1, 2, 3, 6, 8, 9, 45])
sb = set(b) # set([1, 2, 4, 5, 6, 7, 8, 9])
```

### Intersection

Returns a new set with elements common to the set and all others.

```python
sa & sb # set([8, 1, 2, 6])
```

### Union

Returns a new set with elements from the set and all others.

```python
sa | sb # set([1, 2, 3, 4, 5, 6, 7, 8, 9, 45, 89])
```

### Symmetric difference

Returns a new set with elements in either the set or other but not both.

```python
sa ^ sb # set([3, 4, 5, 7, 9, 45, 89])
```

### Difference

Returns a new set with elements in the set that are not in the others.

```python
sa - sb # set([9, 3, 45])
```
