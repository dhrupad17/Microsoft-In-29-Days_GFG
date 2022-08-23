# Find All Four Sum Numbers
---
- ## Question:
> Given an array of integers and another number. Find all the unique quadruple from the given array that sums up to the given number.
---
- ## Example:
> Input: N = 5, K = 3 A[] = {0,0,2,1,1}
> 
> Output: 0 0 1 2 $
> 
> Explanation: Sum of 0, 0, 1, 2 is equal to K.
---
- ## Solution:
**Code :**
```java
class Solution {
    public ArrayList<ArrayList<Integer>> fourSum(int[] arr, int k) {
        // code here
        Set<ArrayList<Integer>> set = new LinkedHashSet<>();
        Arrays.sort(arr);
        for(int i=0;i<=arr.length-2;i++)
        {
            for(int j=i+1;j<=arr.length-1;j++)
            {
                int l=j+1;
                int r=arr.length-1;
                while(l<r){
                    if(arr[i]+arr[j]+arr[l]+arr[r]<k)
                    {
                        l++;
                    }
                    else if(arr[i]+arr[j]+arr[l]+arr[r]>k)
                    {
                        r--;
                    }
                    else
                    {
                        set.add(new ArrayList<>(Arrays.asList(arr[i],arr[j],arr[l],arr[r])));
                        r--;
                    }
                }
            }
        }
        return new ArrayList<>(set);
    }
}
