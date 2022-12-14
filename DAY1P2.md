# Smallest window in a string containing all the characters of another string
---
- ## Question:
> Given two strings S and P. Find the smallest window in the string S consisting of all the characters(including duplicates) of the string P.  Return "-1" in case there is no such window present. In case there are multiple such windows of same length, return the one with the least starting index. 
---
- ## Example:
> Input: S = "timetopractice" P = "toc"
> 
> Output: toprac
> 
> Explanation: "toprac" is the smallest substring in which "toc" can be found.
---
- ## Solution:
**Code :**
```java
class Solution
{
   //Function to find the smallest window in the string s consisting
   //of all the characters of string p.
   public static String smallestWindow(String s, String p)
   {
       // Your code here
       if(s.length()==0 || p.length()==0 || s.length()<p.length())
          return "-1";
       HashMap<Character,Integer> map = new HashMap<Character,Integer>();
       for(char c : p.toCharArray())
       {
           if(map.containsKey(c))
               map.put(c,map.get(c)+1);
           else
               map.put(c,1);
       }
       int count = 0;
       int start = 0;
       int minlength = Integer.MAX_VALUE;
       int minleft = 0;
       for(int i=0;i<s.length();i++)
       {
           char c = s.charAt(i);
           if(map.containsKey(c))
           {
               map.put(c,map.get(c)-1);
               if(map.get(c)>=0)
                   count++;
           }
           while(count == p.length())
           {
               if(minlength>i-start+1)
               {
                   minlength = i-start+1;
                   minleft = start;
               }
               if(map.containsKey(s.charAt(start)))
               {
                   map.put(s.charAt(start),map.get(s.charAt(start))+1);
                   if(map.get(s.charAt(start))>0)
                       count--;
               }
               start++;
           }
       }
       if(minlength>s.length())
           return "-1";
       return s.substring(minleft,minleft+minlength);
   }
}
