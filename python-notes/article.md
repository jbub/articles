# Python notes

Some notes about things you can do in python.

```python
# generate matrix n x n
[[col for col in range(n)] for row in range(n)]

# flatten matrix
[num for row in m for num in row]

# generate identity matrix with the size of n
[[1 if col == row else 0 for row in range(n)] for col in range(n)]

# return a random element from the non empty sequence
random.choice([1, 4, 7, 9]) >>> 7

# return a k length list of unique elements chosen from the population sequence
random.sample([1, 2, 3, 4], 2) >>> [4, 1]

# shuffle the sequence t in place
t = [1, 2, 3]
random.shuffle(t)
t >>> [3, 1, 2]

# return a k length string of random characters chosen from the chars string
''.join(random.sample('abcdefg', 4)) >>> 'afge'

# lists with duplicate items
a = [1, 2, 3]
b = [4, 1, 1, 3, 5]

# notice that there are only unique items in the sets
sa = set(a) 
sa >>> set([1, 2, 3])
sb = set(b) 
sb >>> set([1, 3, 4, 5])

# return a new set with elements common to the set and all others
sa & sb >>> set([1, 3])

# return a new set with elements from the set and all others
sa | sb >>> set([1, 2, 3, 4, 5])

# return a new set with elements in either the set or other but not both
sa ^ sb >>> set([2, 4, 5])

# return a new set with elements in the set that are not in the others
sa - sb >>> set([2])
```
