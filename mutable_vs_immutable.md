# Mutable vs. Immutable Objects in Python

## Introduction
Understanding the difference between **mutable** and **immutable** objects in Python is crucial for understanding how Python manages memory, creating bug-free code, and developing a fundamental comprehension of object oriented programming.  I recently had a technical interview involving lists in Python which where a question similar to the following was asked:

```python
cool_list = [1,2,3,4]
another_cool_list = cool_list
another_cool_list.append(-1)
print(cool_list)
```

**Question:**  What will ```cool_list``` print?  
**My answer:**  ```[1,2,3,4]```
**Correct answer:** ```[1,2,3,4,-1]```  

I beat myself over the head after the interview as I realized my mistake.  
This helpful guide is for myself and all those that wish to not make the same mistake I did!  
Let's get started.


## What is Mutability?
- **Mutable Objects**: Can be modified after creation.
- **Immutable Objects**: Cannot be changed once created.

## Common Mutable Objects
These objects **can be modified in place**:

| Type | Example |
|------|---------|
| `list` | `[1, 2, 3]` |
| `dict` | `{"a": 1, "b": 2}` |
| `set` | `{1, 2, 3}` |
| `bytearray` | `bytearray(b"hello")` |
| Custom Objects | Instances of user-defined classes with mutable attributes |

### Example:
Let's refer back to the original example from the introduction:
```python
cool_list = [1,2,3,4]
another_cool_list = cool_list # Both lists point to the same list!
another_cool_list.append(-1)
print(cool_list) # If I change one list, I change the other similarly!
# Output:  [1,2,3,4,-1]
```
Modifying ```another_cool_list``` automatically updates ```cool_list``` as they both point to the same list in memory.  
### This behavior is similar to all mutable objects. ###

## Common Immutable Objects
These objects **cannot be modified** after creation:

| Type | Example |
|------|---------|
| `int` | `42` |
| `float` | `3.14` |
| `str` | `'hello'` |
| `tuple` | `(1, 2, 3)` |
| `frozenset` | `frozenset({1, 2, 3})` |
| `bytes` | `b"hello"` |

### Example:
```python
x = "hello"
y = x  # Both variables point to the same string object
x += " world"  # Creates a new string object, does not modify the original
print(y)  # Output: 'hello'
```
Here, modifying `x` does not change `y` because a new string object was created.

## Copying Objects: Shallow vs. Deep Copy
If you need an independent copy of a mutable object, use:

### Shallow Copy (Only copies the top-level object, not nested structures)
```python
import copy
original = [[1, 2, 3], [4, 5, 6]]
shallow_copy = copy.copy(original)
shallow_copy[0][0] = 99
print(original)  # Output: [[99, 2, 3], [4, 5, 6]]
```

### Deep Copy (Recursively copies all nested objects)
```python
import copy
original = [[1, 2, 3], [4, 5, 6]]
deep_copy = copy.deepcopy(original)
deep_copy[0][0] = 99
print(original)  # Output: [[1, 2, 3], [4, 5, 6]]
```

## When to Use Mutable vs. Immutable Objects?
- **Use mutable objects** when you need to modify data in place (e.g., appending to lists, updating dictionaries).
- **Use immutable objects** when you need to ensure data integrity (e.g., using tuples as dictionary keys, string manipulation, multi-threaded programming).

## Conclusion
Understanding mutability in Python helps avoid unintended side effects, improves memory efficiency, and makes debugging easier. Mastering this concept is valuable for both performance optimization and code reliability.
