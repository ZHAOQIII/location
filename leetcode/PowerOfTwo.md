## 问题分析： 
给定一个整数，编写一个函数来判断它是否是 2 的幂次方。


## 代码实现
```c
class Solution {
public:
    bool isPowerOfTwo(int n) {
 return (n>0) && (!(n&(n-1)));  
    }
};
```
## 总结：
2的幂次方最高位一定为1。