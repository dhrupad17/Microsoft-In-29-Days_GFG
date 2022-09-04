# Bike Racing
---
- ## Question:
> Geek is organising a bike race with N bikers. The initial speed of the ith biker is denoted by Hi Km/hr and the acceleration of ith biker as Ai Km/Hr2. A biker whose speed is 'L' or more, is considered be a fast biker. The total speed on the track for every hour is calculated by adding the speed of each fast biker in that hour. When the total speed on the track is 'M' kilometers per hour or more, the safety alarm turns on. 
Find the minimum number of hours after which the safety alarm will start.
---
- ## Example:
> Input: 
N = 3, M = 400, L = 120
H = {20, 50, 20}
A = {20, 70, 90}
>
> Output: 3
---
- ## Solution:
**Code :**
```java
class Solution{
   static long buzzTime(int N, long M, long L, long H[], long A[]){
       // code here
       long a=Math.max(L,M), sum=0, res=-1;
       while(sum<=a){
           long mid=sum+(a-sum)/2;
           if(possible(N,M,L,H,A,mid)){
               res=mid;
               a=mid-1;
           }else sum=mid+1;
       }
       return res;
   }
   
   static boolean possible(int N, long M, long L, long H[], long A[], long mid){
       long s=0;
       for(int i=0;i<N;i++){
            long a=H[i]+mid*A[i];
            if(a>=L) s+=a;
       }
       if(s>=M) return true;
       return false;
   }
}
