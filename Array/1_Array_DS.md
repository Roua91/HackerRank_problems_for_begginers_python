# Arrays – DS

## Problem Summary

Given an array of integers, print the elements in **reverse order** on a single line.

---

## Approach 1 — Manual Loop

Build a new array by iterating from the last index down to `0`, appending each element.

```python
def reverseArray(a):
    reversed_list = []
    # Start at the last index (len(a)-1), go to -1 (to include 0), step -1
    for i in range(len(a) - 1, -1, -1):
        reversed_list.append(a[i])
    return reversed_list
```

`range(len(a) - 1, -1, -1)` generates indices from the last position down to `0`. The stop value is `-1` because `range` excludes the stop, so to include index `0` we go one step further.

---

## Approach 2 — Two Pointer Swap

Use two pointers, one at each end, and swap elements moving inward until they meet in the middle. This reverses the array **in place** without needing extra space.

```python
def reverseArray(a):
    left = 0
    right = len(a) - 1

    while left < right:
        # Swap values using Python's tuple unpacking
        a[left], a[right] = a[right], a[left]
        # Move pointers inward
        left += 1
        right -= 1
    return a
```

Each iteration swaps `a[left]` and `a[right]`, then moves the pointers one step closer to the center. When `left >= right`, every element has been swapped and the array is fully reversed.

```
Step 0:  [1, 2, 3, 4, 5]   left=0, right=4  →  swap 1 and 5
Step 1:  [5, 2, 3, 4, 1]   left=1, right=3  →  swap 2 and 4
Step 2:  [5, 4, 3, 2, 1]   left=2, right=2  →  pointers meet, stop
```

---

## Approach 3 — Slice (Pythonic)

Python's slice syntax `[start:stop:step]` can reverse an array in a single line by setting the step to `-1`.

```python
def reverseArray(a):
    # [start:stop:step] - Setting step to -1 reverses the entire sequence
    return a[::-1]
```

Leaving `start` and `stop` empty means "the whole array", and a step of `-1` walks through it backwards. This returns a new reversed copy without modifying the original.

---

## Comparison

| Approach | Extra Space | Modifies Original | Complexity |
|----------|-------------|-------------------|------------|
| Manual Loop | Yes — new list | No | O(n) |
| Two Pointer | No — in place | Yes | O(n) |
| Slice `[::-1]` | Yes — new list | No | O(n) |

All three approaches are O(n). The **slice** is the most concise, the **two pointer** is the most memory efficient, and the **manual loop** makes the logic the most explicit.
