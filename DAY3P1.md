# Count Inversions
---
- ## Question:
> Given an array of integers. Find the Inversion Count in the array. 
> 
> Inversion Count: For an array, inversion count indicates how far (or close) the array is from being sorted. If array is already sorted then the inversion count is 0. If an array is sorted in the reverse order then the inversion count is the maximum. 
> 
> Formally, two elements a[i] and a[j] form an inversion if a[i] > a[j] and i < j.
---
- ## Example:
> Input: N = 5, arr[] = {2, 4, 1, 3, 5}
> 
> Output: 3
---
- ## Solution:
**Code :**
```java
class Solution
{
    // arr[]: Input Array
    // N : Size of the Array arr[]
    //Function to count inversions in the array.
    static long inversionCount(long arr[], long N)
    {
        // Your Code Here
        long[] temp=new long[arr.length];
        long ans=findmerge(arr,temp,0,arr.length-1);
        return ans;
    }
    public static long findmerge(long[] arr, long[] temp,int left,int right)
    {
        int mid=0;
        long count=0;
        if(right>left)
        {
            mid=(left+right)/2;
            count=count+findmerge(arr,temp,left,mid);
            count=count+findmerge(arr,temp,mid+1,right);
            count=count+merge(arr,temp,left,mid+1,right);
        }
        return count;
    }
    public static long merge(long[] arr, long[] temp,int left, int mid,int right)
    {
        int i,j,k;
        long count=0;
        i=left;
        j=mid;
        k=left;
        while(i<=mid-1 && j<=right)
        {
            if(arr[i]<=arr[j])
            {
                temp[k++]=arr[i++];
            }
            else
            {
                temp[k++]=arr[j++];
                count=count+(mid-i);
            }
        }
        while(i<=mid-1)
        {
            temp[k++]=arr[i++];
        }
        while(j<=right)
        {
            temp[k++]=arr[j++];
        }
        for(i=left;i<=right;i++)
        {
            arr[i]=temp[i];
        }
        return count;
    }
}
