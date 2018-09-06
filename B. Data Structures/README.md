# Cheat Sheet

## Lists
A mutable, ordered collection of (similar) elements.

### Creation
```python
>>> letters = ['a', 'b', 'c']
```

### Zero-Indexing
```python
>>> letters[1]
'b'
```

### Negative Indexing
```python
>>> letters[-3]
'a'
```

### Adding elements
```python
>>> # The following methods return None
>>> # but have the side effect of modifying the list
>>> letters.append('d')
>>> letters.extend(['f', 'g'])
>>> letters.insert(4, 'e')
>>> letters
['a', 'b', 'c', 'd', 'e', 'f', 'g']
```

### Removing elements
```python
>>> letters.pop()
'g'
>>> letters.pop(0)
'a'
>>> letters
['b', 'c', 'd', 'e', 'f']
```

### Checking membership
```python
>>> 'c' in letters
True
>>> 'C' in letters
False
```

### Getting the list size
```python
>>> letters = ['b', 'c', 'd', 'e', 'f']
>>> len(letters)
5
```

### Sorting

#### Get sorted version
```python
>>> numbers = [7, 5, 9, 3, 1]
>>> sorted(numbers)
[1, 3, 5, 7, 9]
>>> numbers
[7, 5, 9, 3, 1]
```

#### Sorting in place
```python
>>> # Note that this method returns None
>>> numbers.sort()
>>> numbers
[1, 3, 5, 7, 9]
```

#### Sorting complex objects
```python
>>> tuples = [("Charles", 5), ("Diana", 1)]
>>> sorted(tuples)
[('Charles', 5), ('Diana', 1)]
>>> sorted(tuples, key=lambda pair: pair[1])
[('Diana', 1), ('Charles', 5)]
```

### Slicing
Used for getting positional subsets of a list. Typically used on sorted lists.

General idea: `list_name[start:end:step]`
- `start` is an inclusive bound and defaults to 0
- `end` is an exclusive bound and defaults to end of list (by not specifying a number)
- `step` defaults to 1

```python
>>> letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h']
>>> letters[:2]
['a', 'b']

>>> letters[1:2]
['b']

>>> letters[-3:]
['f', 'g', 'h']

>>> letters[1::2]
['b', 'd', 'f', 'h']
```

### List Comprehensions
A list comprehension converts any iterable (typically a list) to a new list.

It is very powerful and can be used for transforming a list, filtering a list, or both.

```python
>>> letters = ['a', 'b', 'c', 'd', 'e', 'f']
>>> [letter.upper() for letter in letters if letter > 'c']
['D', 'E', 'F']
```
- `letter.upper()` is the transformation (uppercasing)
- 'for letter in letters' is what defines `letter`: It represents each element in the `letters` list as we loop through it.
- `if letter > 'c'` is the condition: Only include letters after `'c'` in the output list.
