## 问题分析： 
给定一个正整数 n，将其拆分为至少两个正整数的和，并使这些整数的乘积最大化。 返回你可以获得的最大乘积。
## 代码实现
```c
class Solution {
public:
    int integerBreak(int n) {
      int max=1;
        if(n==2)return 1;
        if(n==3){return 2;}
    while(n>4){
        max=max*3;
        n=n-3;
    }max=max*n;
        return max;
    }
};
```
## 总结：
可以把n拆分成实数。那么设每一个数为x,则一共有n/x个数。设它们的积为f(x),则f(x)=x(n/x)，那么怎么求f(x)最大值呢？求导数！f′(x)=(n/x^2)  *  x^(n/x)  * (1-lnx)当x=e时取极大值。题目里规定x为整数，那么只需要取的x越靠近e越好。那么2<e<3，而且e=2.71828...，所以取3是最好的，拆出足够多的 3 就能使得乘积最大。
      
      