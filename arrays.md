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

    def twoSum(self, nums: List[int], target: int) -> List[int]:
        numsdict = {}
        for i, elem in enumerate(nums):
            n = target - elem
            if n not in numsdict:
                numsdict[elem] = i
            else:
                return[numsdict[n],i]
