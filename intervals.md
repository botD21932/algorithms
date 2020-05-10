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
        if(intervals == []):
            return 0
        intervals.sort(key = lambda x: x[0])
        end = (intervals[0])[1]
        min = 0
        for i in range(1,len(intervals)):
            if((intervals[i])[0] < end):
                if(intervals[i][1] < end):
                    end = intervals[i][1]
                min = min + 1
            else:
                end = (intervals[i])[1]
        return min
