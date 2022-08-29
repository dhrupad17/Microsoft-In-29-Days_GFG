# Count the number of possible triangles
---
- ## Question:
> Given an unsorted array arr[] of n positive integers. Find the number of triangles that can be formed with three different array elements as lengths of three sides of triangles. 
---
- ## Example:
> Input: 
n = 3
arr[] = {3, 5, 4}
>
> Output: 
1
---
- ## Solution:
**Code :**
```java
class Solution
{
    //Function to count the number of possible triangles.
    static int findNumberOfTriangles(int arr[], int n)
    {
        // code here
        int count=0;
        Arrays.sort(arr);
        int one=0;
        int left=0;
        int right=0;
        for(int i=n-1;i>=2;i--)
        {
            one=arr[i];
            count=count+twosum(0,i-1,arr,one);
        }
        return count;
    }
    static int twosum(int left, int right, int arr[], int sum)
    {
        int count=0;
        while(left<right)
        {
            if(arr[left]+arr[right]>sum)
            {
                count=count+(right-left);
                right--;
            }
            else
                left++;
        }
        return count;
    }
}
