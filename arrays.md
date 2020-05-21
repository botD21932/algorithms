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

```python
def threeSum(self, nums: List[int]) -> List[List[int]]:
    nums.sort()
    result = []
    for first in range(len(nums)-2):
        if first > 0 and nums[first] == nums[first-1]:
            continue
        second = first+1
        third = len(nums) - 1
        while second < third:
            sum = nums[first] + nums[second] + nums[third]
            if sum < 0:
                second = second + 1
            elif sum > 0:
                third = third - 1
            else:
                result.append([nums[first], nums[second], nums[third]])
                while second < third and nums[second] == nums[second+1]:
                    second = second + 1
                while third > second and nums[third] == nums[third-1]:
                    third = third - 1
                second = second + 1
                third = third - 1
    return result
    
```

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
