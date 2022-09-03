# Check if two strings are k-anagrams or not
---
- ## Question:
> Given two strings of lowercase alphabets and a value K, your task is to complete the given function which tells if  two strings are K-anagrams of each other or not.
> 
> Two strings are called K-anagrams if both of the below conditions are true.
> 
> 1. Both have same number of characters.
> 
> 2. Two strings can become anagram by changing at most K characters in a string.
---
- ## Example:
> Input:
str1 = "fodr", str2="gork"
k = 2
>
> Output:
1
>
> Explanation: Can change fd to gk
---
- ## Solution:
**Code :**
```java
class Solution {
    boolean areKAnagrams(String s1, String s2, int k) {
        // code here
        if(s1.length()!=s2.length())
            return false;
        int[] arr=new int[26];
        for(int i=0;i<s1.length();i++){
            arr[s1.charAt(i)-'a']++;
        }
        for(int i=0;i<s2.length();i++){
            char ch=s2.charAt(i);
            if(arr[ch-'a']>0)
                arr[ch-'a']--;
        }
        int count=0;
        for(int i=0;i<26;i++)
        {
            if(arr[i]>0)
                count=count+arr[i];
        }
        return count<=k;
    }
}
