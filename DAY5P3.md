# Implement Atoi
---
- ## Question:
> Your task  is to implement the function atoi. The function takes a string(str) as argument and converts it to an integer and returns it.
> 
> Note: You are not allowed to use inbuilt function.
---
- ## Example:
> Input:
str = 123
>
> Output: 123
---
- ## Solution:
**Code :**
```java
class Solution
{
    int atoi(String s) {
	// Your code here
	boolean pos=true;
	int i=0;
	int ans=0;
	if(s.charAt(i)=='-')
	{
	    pos=false;
	    i++;
	}
	while(i<s.length())
	{
	    char ch=s.charAt(i);
	    if(ch<'0'|| ch>'9'){
	        return -1;
	    }
	    else{
	        int num=ch-'0';
	        ans=ans*10+num;
	    }
	    i++;
	}
	if(pos==true)
	    return ans;
	return ans*-1;
    }
}
