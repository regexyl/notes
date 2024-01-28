It can come in the form of 1D or 2D prefix sum matrices, or even hashmaps.

#### Hashmap
- If the prefix sum is represented by `sum[i]` where each element is the sum from index 0 to the `i` index, the difference between two elements with the same cumulative sum is 0.
- Similarly, if the difference between `sum[j]` and `sum[i]` is `k`,  then the elements lying between indices `j` and `i` has a sum of `k`

![[Pasted image 20240128134045.png]]

Example from [Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)
(Also can be solved with a 1D prefix sum matrix)
```python
def subarraySum(self, nums: List[int], k: int) -> int:
	result = 0 
	prefix_sum = 0
	d = {0 : 1}

	for num in nums:
		prefix_sum = prefix_sum + num

		if prefix_sum - k in d:
			result = result + d[prefix_sum - k]
		if prefix_sum not in d:
			d[prefix_sum] = 1
		else:
			d[prefix_sum] = d[prefix_sum] + 1

	return result
```