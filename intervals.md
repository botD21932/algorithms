# Intervals

+ [Insert Interval](#insert-interval)
+ [Merge Intervals](#merge-intervals)
+ [Non-overlapping Intervals](#non-overlapping-intervals)

## Insert Interval

https://leetcode.com/problems/insert-interval/

## Merge Intervals

https://leetcode.com/problems/merge-intervals/

## Non-overlapping Intervals

https://leetcode.com/problems/non-overlapping-intervals

  def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
        if not intervals:
            return 0
        intervals.sort(key = lambda x: x[0])
        end = (intervals[0])[1]
        min = 0
        for elem in intervals[1::]:
            if(elem[0] < end):
                if(elem[1] < end):
                    end = elem[1]
                min = min + 1
            else:
                end = elem[1]
        return min
