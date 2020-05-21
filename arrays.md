# Arrays

+[Subarray Sum Equals K](#subarray-sum-equals-k)
+[3Sum](#3sum)
+[Two Sum](#two-sum)

## Subarray Sum Equals K

https://leetcode.com/problems/subarray-sum-equals-k/

```python
def subarraySum(self, nums: List[int], k: int) -> int:
    count = 0
    sum = 0
    d = {0: 1}
    for i in range(len(nums)):
        sum = sum + nums[i]
        if(sum - k in d.keys()):
            count = count + d.get(sum - k)
        d.update({sum: d.setdefault(sum, 0) + 1})
    return count

```

## 3Sum

https://leetcode.com/problems/3sum/

## Two Sum

https://leetcode.com/problems/two-sum/
