# Factorials of large numbers
---
- ## Question:
> Given an integer N, find its factorial.
---
- ## Example:
> Input: N = 5
> 
> Output: 120
> 
> Explanation : 5! = 1*2*3*4*5 = 120
---
- ## Solution:
**Code :**
```java
class Solution {
    static ArrayList<Integer> factorial(int n){
        //code here
        ArrayList<Integer> list=new ArrayList<>();
        list.add(1);
        for(int i=1;i<=n;i++)
        {
            int c=0;
            for(int j=0;j<list.size();j++)
            {
                int res=(list.get(j)*i)+c;
                c=res/10;
                list.set(j,res%10);
            }
            while(c!=0)
            {
                list.add(c%10);
                c=c/10;
            }
        }
        Collections.reverse(list);
        return list;
    }
}
