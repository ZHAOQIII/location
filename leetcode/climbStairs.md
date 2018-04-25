## 问题分析： 
假设你正在爬楼梯。需要 n 步你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？

注意：给定 n 是一个正整数。


## 代码实现
```c
class Solution {
public:
    int climbStairs(int n) {
      int i;
      int a[n];
    
      for(i=0;i<n;i++)
      {
        if(i==0||i==1)a[i]=i+1;
          else a[i]=a[i-1]+a[i-2];
      }
        return a[i-1];
    }
};
```
## 总结：
假设要爬n个台阶，则是由n-2或n-1一步爬上的，以此类推。