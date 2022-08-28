# Sort array after converting elements to their squares
---
- ## Question:
> Given an array A consisting of both positive and negative integers of size N which are sorted. Your task is to sort the square of the numbers of the array.
---
- ## Example:
> Input:
N = 6
A[] = {-6, -3, -1, 2, 4, 5}
>
> Output: 1 4 9 16 25 36
---
- ## Solution:
**Code :**
```java
class Solution{
	public int[] sortSquares(int[] arr,int n){
		//Write your code here
		for(int i=0;i<n;i++)
		{
		    arr[i]=arr[i]*arr[i];
		}
		Arrays.sort(arr);
		return arr;
	}
}
