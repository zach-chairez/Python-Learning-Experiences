
# Mutable vs. Immutable Objects in Python

## Introduction
Understanding the difference between **mutable** and **immutable** objects in Python is crucial for understanding how Python manages memory, creating bug-free code, and developing a fundamental comprehension of object oriented programming.  I recently had a technical interview involving lists in Python - the following code and question were given:

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
| `list` | `["bloop", 23, "hello moto"]` |
| `dict` | `{"country": vietnam, "population": "a few"}` |
| `set` | `{1, 2, 3}` |
| `bytearray` | `bytearray(b"2356")` |
| Custom Objects | When we create an instance of a class with defined methods |

### Example:
Let's refer back to the original example from the introduction:
```python
cool_list = [1,2,3,4]
another_cool_list = cool_list # Both lists point to the same list object!
another_cool_list.append(-1)
print(cool_list) # If I change one list, I change the other!
# Output:  [1,2,3,4,-1]
```
Modifying ```another_cool_list``` automatically updates ```cool_list``` as they both point to the same list in memory.  
### This behavior is similar to all mutable objects. ###

## Common Immutable Objects
These objects **cannot be modified** after creation:

| Type | Example |
|------|---------|
| `int` | `42` |
| `float` | `3.14159` |
| `str` | `'pineapple belongs on pizza'` |
| `tuple` | `(-1, 0, 1)` |
| `frozenset` | `frozenset({1, 2, 3})` |
| `bytes` | `b"salutations"` |

### Example:
```python
my_string = "my name is"
new_string = my_string  # Both variables point to the same string object!
new_string += "jeff"  # Add "jeff" to new_string
print(my_string)  # Output: 'my name is'
```
Here, modifying `new_string` does not change `my_string` because a new string object was created from an immutable one.

## Copying Objects: Shallow vs. Deep Copy
**Question:** What if want to copy the contents of a mutable object to a new variable so that we don't change the original object while updating the new variable? 

**Answer:** We make copies!

### Shallow Copy (Only copies the top-level object, not nested structures)
```python
import copy
original_list = [[1, 2, 3], [4, 5, 6]]

# Copy - Method 1 for lists
copied_list = original_list.copy()

# Copy - Method 2 for lists
# copied_list = original_list[:]

# Copy - Method 3 for lists and all other objects
# copied_list = copy.copy(original_list)

# Update the value 2 to 23
copied_list[0][1] = 23

# Print contents of original list
print(original_list)  # Output: [[1, 23, 3], [4, 5, 6]]
```

When we make a (shallow) copy of a mutable object, only the outer object points to a different object while the 
internal structures are still pointing to the same object.  

It's still something I struggle with, but I know with more practice and experience, it will become more intuitive.

Here's another example:

```python
import copy
original_list = [[1, 2, 3], [4, 5, 6]]

# Copy - Method 1 for lists
copied_list = original_list.copy()

# Copy - Method 2 for lists
# copied_list = original_list[:]

# Copy - Method 3 for lists and all other objects
# copied_list = copy.copy(original_list)

# Update the copied list's internal list [1, 2, 3] to [-1, -2, -3]
copied_list[0] = [-1,-2,-3]

# Print contents of original list
print(original_list)  # Output: [[1, 2, 3], [4, 5, 6]]
print(copied_list) # Output: [[-1,-2,-3],[4, 5, 6]]  
```
We see above that the original list was unaffected because we made a copy of the outer structure of ```original_list``` and not its internal structures.  

If we want to avoid these nuances, we can use **deepcopies** instead!

### Deep Copy (Recursively copies all nested objects)
```python
import copy
original_list = [[1, 2, 3], [4, 5, 6]]

# Create a deep copy and update an entry
deep_copied_list = copy.deepcopy(original_list)
deep_copied_list[0][0] = 23

# Print results
print(original_list)  # Output: [[1, 2, 3], [4, 5, 6]]
print(deep_copied_list) # Output: [[23, 2, 3],[4, 5, 6]]
```
