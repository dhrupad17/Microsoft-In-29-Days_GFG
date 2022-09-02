# Longest Palindrome in a String
---
- ## Question:
> Given a string S, find the longest palindromic substring in S. Substring of string S: S[ i . . . . j ] where 0 ≤ i ≤ j < len(S). Palindrome string: A string which reads the same backwards. More formally, S is palindrome if reverse(S) = S. Incase of conflict, return the substring which occurs first ( with the least starting index).
---
- ## Example:
> Input:
S = "aaaabbaa"
>
> Output: aabbaa
---
- ## Solution:
**Code :**
```java
class Solution{
    static int start,end;
     static int countpalin(String s,int i,int j,int n){
        int cnt = 0;
        while(i>=0 && j<n && s.charAt(i)==s.charAt(j)){
            cnt++;
            i--;
            j++;
        }
        start = i+1;
        end = j-1;
        return cnt;
    }
    static String longestPalin(String s){
        // code here
        int n=s.length();
        start=0;
        end=0;
        int ans=Integer.MIN_VALUE;
        String res="";
        for(int i=0;i<n-1;i++)
        {
            int even=countpalin(s,i,i+1,n)*2;
            if(even>ans)
            {
                ans=even;
                res=s.substring(start,end+1);
            }
            int odd=countpalin(s,i-1,i+1,n)*2+1;
            if(odd>ans)
            {
                ans=odd;
                res=s.substring(start,end+1);
            }
        }
        if(res.length()<=1){
            return s.substring(0,1);
        }
        return res;
    }
}
