# Intervals

+ [Insert Interval](#insert-interval)
+ [Merge Intervals](#merge-intervals)
+ [Non-overlapping Intervals](#non-overlapping-intervals)

## Insert Interval

https://leetcode.com/problems/insert-interval/

```python
def insert(self, intervals: List[List[int]], newInterval: List[int]) -> List[List[int]]:
      intervals.append(newInterval)
      intervals = sorted(intervals, key=lambda x: x[0])
      result = []
      for interval in intervals:
          if not result or result[-1][1] < interval[0]:
              result.append(interval)
          else:
              result[-1][1] = max(result[-1][1], interval[1])
      return result

```

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

```python
def merge(self, intervals: List[List[int]]) -> List[List[int]]:
      intervals = sorted(intervals, key=lambda x: x[0])
      result = []
      for interval in intervals:
          if not result or result[-1][1] < interval[0]:
              result.append(interval)
          else:
              result[-1][1] = max(result[-1][1], interval[1])
      return result
      
```

## Non-overlapping Intervals

https://leetcode.com/problems/non-overlapping-intervals

```python
def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
    if not intervals:
        return 0
    intervals.sort(key=lambda x: x[1])
    end = (intervals[0])[1]
    min = 0
    for elem in intervals[1::]:
        if elem[0] < end:
            min = min + 1
        else:
            end = elem[1]
    return min
    
 ```
