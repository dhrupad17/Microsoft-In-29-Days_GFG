# Overlapping Intervals
---
- ## Question:
> Given a collection of Intervals, the task is to merge all of the overlapping Intervals.
---
- ## Example:
> Input:
Intervals = {{1,3},{2,4},{6,8},{9,10}}
>
> Output: {{1, 4}, {6, 8}, {9, 10}}
---
- ## Solution:
**Code :**
```java
class Solution
{
    public int[][] overlappedInterval(int[][] Intervals)
    {
        // Code here
        Arrays.sort(Intervals,new Comparator<int[]>(){
           @Override
           public int compare(final int arr1[],final int arr2[])
           {
               if(arr1[0]>arr2[0])
                    return 1;
                else
                    return -1;
           }
        });
        ArrayList<Integer> arr=new ArrayList<>();
        int prev=Intervals[0][1];
        arr.add(Intervals[0][0]);
        for(int i=1;i<Intervals.length;i++)
        {
            if(prev>=Intervals[i][0]){
                if(prev>=Intervals[i][1])
                    continue;
                else
                    prev=Intervals[i][1];
            }
            else
            {
                arr.add(prev);
                arr.add(Intervals[i][0]);
                prev=Intervals[i][1];
            }
        }
        arr.add(prev);
        int n=arr.size()/2;
        int j=0;
        int ans[][]=new int[n][2];
        for(int i=0;i<n;i++)
        {
            ans[i][0]=arr.get(j);
            j++;
            ans[i][1]=arr.get(j);
            j++;
        }
        return ans;
    }
}
