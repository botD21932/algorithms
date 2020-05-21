# Arrays

+[Subarray Sum Equals K](#subarray-sum-equals-k)
+[3Sum](#3sum)
+[Two Sum](#two-sum)

## Subarray Sum Equals K

https://leetcode.com/problems/subarray-sum-equals-k/

## 3Sum

https://leetcode.com/problems/3sum/

## Two Sum

https://leetcode.com/problems/two-sum/

```python
def twoSum(self, nums: List[int], target: int) -> List[int]:
    numsdict = {}
    for i, elem in enumerate(nums):
        n = target - elem
        if n not in numsdict:
            numsdict[elem] = i
        else:
            return[numsdict[n], i]


def twoSum(self, nums: List[int], target: int) -> List[int]:
    nums = [elem for elem in enumerate(nums)]
    nums.sort(key=lambda x: x[1])
    begin = 0
    end = len(nums) - 1
    while begin != end:
        if nums[begin][1] + nums[end][1] == target:
            return [nums[begin][0], nums[end][0]]
        elif nums[begin][1] + nums[end][1] < target:
            begin = begin + 1
        else:
            end = end - 1

```
