## Question:
You are given an integer array nums of size n and q queries. Each query contains two integers L and R (0-indexed), representing a subarray.
For every query, return the sum of elements from index L to R.
## Example:
```python
nums = [3, 1, 4, 1, 5, 9]

queries = [
  [1, 3],
  [2, 5],
  [0, 4]
]

Output:
6
19
14

```

## Solution 

```python
def range_sum_queries(nums, queries):
    # Build prefix sum
    prefix = [0] * (len(nums) + 1)

    for i in range(len(nums)):
        prefix[i + 1] = prefix[i] + nums[i]

    # Answer queries
    result = []
    for L, R in queries:
        result.append(prefix[R + 1] - prefix[L])

    return result


# Example
nums = [3, 1, 4, 1, 5, 9]
queries = [(1, 3), (2, 5), (0, 4)]

print(range_sum_queries(nums, queries))
```
