## Level 1 (Fixed-Size Sliding Window)

### These use a window of fixed length k.

Maximum Sum Subarray of Size K ⭐⭐⭐⭐⭐
Find the maximum sum of any contiguous subarray of size k.

### Example:
``` python
nums = [2, 1, 5, 1, 3, 2]
k = 3
```
### Output:
```bash
9
```
- First Negative Number in Every Window of Size K
- Count Distinct Elements in Every Window
- Maximum Element in Every Window (Deque)
- Average of Every Window


## solution
```python
def maxSumSubarrayOfSizeK(nums, k):
    """
    Find the maximum sum of any contiguous subarray of size k.
    
    Time Complexity: O(n)
    Space Complexity: O(1)
    """
    if k > len(nums):
        return None
    
    # Calculate sum of first window
    window_sum = sum(nums[:k])
    max_sum = window_sum
    
    # Slide the window through the rest of the array
    for i in range(k, len(nums)):
        # Remove leftmost element, add rightmost element
        window_sum = window_sum - nums[i - k] + nums[i]
        max_sum = max(max_sum, window_sum)
    
    return max_sum

# Test with your example
nums = [2, 1, 5, 1, 3, 2]
k = 3
print(maxSumSubarrayOfSizeK(nums, k))  # Output: 9
```
