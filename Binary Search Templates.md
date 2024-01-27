
```table-of-contents
```
### Returns result straight within `while` loop

#### Characteristics
- Use `<=` for while loop
- Result **is** derived from *within* the binary search, i.e. if no result is returned, target cannot be found
	- Unlike other types of binary searches where result is defined from `lo` or `hi` - refer to #todo <insert new template here?>

#### Examples
##### Example from [Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/)
```python
def searchMatrix(self, matrix, target):
    m, n = len(matrix), len(matrix[0])
    lo, hi = 0, m * n - 1

    while lo <= hi: # use `<=`
        mid = lo + (hi - lo) // 2
        row, col = mid // n, mid % n

        if matrix[row][col] == target:
            return True # return directly from binary search
        elif target < matrix[row][col]:
            hi = mid - 1
        else:
            lo = mid + 1
    
    return False # only when target cannot be found
```
##### Example from [Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)
```python
def search(self, nums: List[int], target: int) -> int:
    lo, hi = 0, len(nums) - 1

    while lo < hi:
        mid = (hi + lo) // 2

        if nums[mid] == target:
            return mid
        if nums[mid] < target:
            if nums[hi] < nums[lo]:
                lo = mid + 1
            else:
                hi = lo + 1
        else:
            if nums[hi] < nums[lo]:
                lo = mid + 1
            else:
                hi = mid - 1

    return -1
```

### Returns result outside of `while` loop (via `lo` or `hi`)
#### Characteristics


#### Examples
##### Example from [Koko Eating Bananas](https://leetcode.com/problems/koko-eating-bananas/)
```python
def minEatingSpeed(self, piles, h):
    lo, hi = 1, max(piles)

    while lo < hi:
        mid = (hi + lo) // 2
        isAbleToFinish = sum([math.ceil(p / mid) for p in piles]) <= h

        if isAbleToFinish:
            hi = mid
        else:
            lo = mid + 1
    
    return hi
```
