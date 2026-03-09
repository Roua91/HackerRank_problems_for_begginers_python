# Arrays in Python

## What is an Array?

An array is a collection of items stored in a single variable, in a specific order. Think of it like a row of boxes, where each box holds a value and has a number (called an **index**) so you can find it.

```
Index:  0    1    2    3    4
      +----+----+----+----+----+
      | 10 | 20 | 30 | 40 | 50 |
      +----+----+----+----+----+
```

In Python, arrays are built using **lists**. A list can hold anything — numbers, strings, or a mix of both.

```python
numbers = [10, 20, 30, 40, 50]
names   = ["Alice", "Bob", "Charlie"]
mixed   = [1, "hello", 3.14]
```

---

## Indexing

Every element in an array has an index. Python indexing starts at `0`, not `1`.

```python
arr = [10, 20, 30, 40, 50]

arr[0]   # → 10  (first element)
arr[2]   # → 30  (third element)
arr[-1]  # → 50  (last element)
arr[-2]  # → 40  (second to last)
```

Negative indexes count backwards from the end, which is useful when you don't know the length of the array.

---

## Slicing

Slicing lets you grab a portion of the array using the format `arr[start:end:step]`.

```python
arr = [10, 20, 30, 40, 50]

arr[1:4]    # → [20, 30, 40]   (index 1 up to, but not including, 4)
arr[:3]     # → [10, 20, 30]   (from the beginning up to index 3)
arr[2:]     # → [30, 40, 50]   (from index 2 to the end)
arr[::-1]   # → [50, 40, 30, 20, 10]  (the whole array, reversed)
```

The `end` index is **not included** in the result — keep that in mind.

---

## Common Methods

### `append()` — Add an element to the end
```python
arr = [1, 2, 3]
arr.append(4)
# arr → [1, 2, 3, 4]
```

### `insert()` — Add an element at a specific position
```python
arr = [1, 2, 3]
arr.insert(1, 99)
# arr → [1, 99, 2, 3]
```

### `remove()` — Remove the first occurrence of a value
```python
arr = [1, 2, 3, 2]
arr.remove(2)
# arr → [1, 3, 2]
```

### `pop()` — Remove and return an element by index
```python
arr = [1, 2, 3]
arr.pop()     # removes last element → returns 3
arr.pop(0)    # removes element at index 0 → returns 1
```

### `sort()` — Sort the array in place
```python
arr = [3, 1, 4, 1, 5]
arr.sort()
# arr → [1, 1, 3, 4, 5]

arr.sort(reverse=True)
# arr → [5, 4, 3, 1, 1]
```

### `reverse()` — Reverse the array in place
```python
arr = [1, 2, 3]
arr.reverse()
# arr → [3, 2, 1]
```

### `index()` — Find the position of a value
```python
arr = [10, 20, 30]
arr.index(20)   # → 1
```

### `count()` — Count how many times a value appears
```python
arr = [1, 2, 2, 3, 2]
arr.count(2)   # → 3
```

### `len()` — Get the number of elements
```python
arr = [10, 20, 30]
len(arr)   # → 3
```

---

## Iterating Over an Array

```python
arr = [10, 20, 30]

# Basic loop
for item in arr:
    print(item)

# Loop with index using enumerate()
for i, item in enumerate(arr):
    print(i, item)
# 0 10
# 1 20
# 2 30
```

---

## Quick Reference

| Operation | Syntax | Description |
|-----------|--------|-------------|
| Access | `arr[i]` | Get element at index `i` |
| Slice | `arr[start:end]` | Get a sub-array |
| Reverse | `arr[::-1]` | Return reversed copy |
| Add to end | `arr.append(x)` | Add `x` at the end |
| Insert | `arr.insert(i, x)` | Add `x` at index `i` |
| Remove value | `arr.remove(x)` | Remove first `x` |
| Remove by index | `arr.pop(i)` | Remove element at index `i` |
| Sort | `arr.sort()` | Sort in place |
| Reverse | `arr.reverse()` | Reverse in place |
| Length | `len(arr)` | Number of elements |
