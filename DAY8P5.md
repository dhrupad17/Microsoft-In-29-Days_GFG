# Median in a row-wise sorted Matrix
---
- ## Question:
> Given a row wise sorted matrix of size RxC where R and C are always odd, find the median of the matrix.
---
- ## Example:
> Input:
R = 3, C = 3
M = [[1, 3, 5], 
     [2, 6, 9], 
     [3, 6, 9]]
>
> Output: 5
---
- ## Solution:
**Code :**
```java
class Solution {
    int median(int matrix[][], int r, int c) {
        // code here        
        int[] arr=new int[r*c];
        int n=0;
        for(int i=0;i<r;i++)
        {
            for(int j=0;j<c;j++)
            {
                arr[n]=matrix[i][j];
                n++;
            }
        }
        Arrays.sort(arr);
        int x=n/2;
        return arr[x];
    }
}
