# Square root of a number
---
- ## Question:
> Given an integer x, find the square root of x. If x is not a perfect square, then return floor(√x).
---
- ## Example:
> Input:
x = 5
>
> Output: 2
---
- ## Solution:
**Code :**
```java
class Solution
{
     long floorSqrt(long x)
	 {
		// Your code here
		long result=(long)Math.floor(Math.sqrt(x));
		return result;
	 }
}
