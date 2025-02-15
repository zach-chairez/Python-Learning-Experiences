# The Big 4 Data Structures of Python: Lists, Tuples, Sets, and Dictionaries

## References:
- [Lists](https://www.w3schools.com/python/python_ref_list.asp)
- [Dictionaries](https://www.w3schools.com/python/python_ref_dictionary.asp)
- [Tuples](https://www.w3schools.com/python/python_ref_tuple.asp)
- [Sets](https://www.w3schools.com/python/python_ref_set.asp)
- [Other structures not listed in this document](https://www.w3schools.com/python/python_reference.asp)

## Lists
### Attributes:
- **Ordered**: Lists maintain the order of elements.
- **Mutable**: Elements can be changed, added, or removed.
- **Allows Duplicates**: Lists can have duplicate values.
- **Indexable**: Supports zero-based indexing.
- **Heterogeneous**: Can store different data types.

### Methods:
- `append(value)`: Adds a single element to the end of the list.
- `extend(iterable)`: Can add multiple elements to the end of a list.
- `insert(index, value)`: Inserts a value at a specified index.
- `remove(value)`: Removes the first occurrence of a value.
- `pop(index)`: Removes and returns an element at the given index.
- `index(value, start, end)`: Returns the index of the first occurrence of a value.
- `count(value)`: Returns the number of times a value appears in the list.
- `reverse()`: Reverses the order of elements.
- `sort(key=None, reverse=False)`: Sorts the list in place.
- `copy()`: Returns a shallow copy of the list.
- `clear()`: Removes all elements.

## Tuples
### Attributes:
- **Ordered**: Maintains insertion order.
- **Immutable**: Cannot be modified after creation.
- **Allows Duplicates**: Elements can repeat.
- **Indexable**: Supports zero-based indexing.
- **Heterogeneous**: Can store different data types.
- **Hashable (if all elements are hashable)**: Can be used as dictionary keys.

### Methods:
- `count(value)`: Returns the number of times a value appears.
- `index(value, start, end)`: Returns the index of the first occurrence of a value.

## Sets
### Attributes:
- **Unordered**: Elements are not stored in a specific order.
- **Mutable**: Elements can be added or removed.
- **No Duplicates**: Stores only unique values.
- **Heterogeneous**: Can store different data types.
- **Unindexed**: Cannot access elements by index.

### Methods:
- `add(value)`: Adds an element to the set.
- `remove(value)`: Removes an element (raises an error if not found).
- `discard(value)`: Removes an element (does not raise an error if not found).
- `pop()`: Removes and returns a random element.
- `clear()`: Removes all elements.
- `union(set2)`: Returns a new set with elements from both sets.
- `intersection(set2)`: Returns a set of common elements.
- `difference(set2)`: Returns elements in the first set but not in the second.
- `symmetric_difference(set2)`: Returns elements in either set but not both.
- `issubset(set2)`: Checks if the set is a subset of another.
- `issuperset(set2)`: Checks if the set is a superset of another.
- `isdisjoint(set2)`: Checks if two sets have no common elements.
- `update(set2)`: Adds elements from another set.
- `intersection_update(set2)`: Keeps only elements found in both sets.
- `difference_update(set2)`: Removes elements found in another set.
- `symmetric_difference_update(set2)`: Keeps only elements unique to each set.
- `copy()`: Returns a shallow copy of the set.

## Dictionaries
### Attributes:
- **Key-Value Pairs**: Stores data in `{key: value}` format.
- **Mutable**: Values can be modified, added, or removed.
- **Unordered (before Python 3.7)**: Order is not guaranteed (since 3.7+, insertion order is preserved).
- **No Duplicate Keys**: Keys must be unique.
- **Heterogeneous**: Keys and values can be different data types.

### Methods:
- `dict[key] = value`: Adds or updates a key-value pair.
- `update(dict2)`: Updates dictionary with key-value pairs from another.
- `get(key, default)`: Returns the value for a key, or a default value if missing.
- `keys()`: Returns all keys.
- `values()`: Returns all values.
- `items()`: Returns key-value pairs as tuples.
- `pop(key, default)`: Removes and returns the value of a key.
- `popitem()`: Removes and returns the last inserted key-value pair.
- `del dict[key]`: Deletes a specific key.
- `clear()`: Removes all key-value pairs.
- `copy()`: Returns a shallow copy of the dictionary.
- `fromkeys(iterable, value)`: Creates a dictionary with specified keys and values.
- `setdefault(key, default)`: Returns the value of a key, or sets it to a default if missing.
