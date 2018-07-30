## 问题分析： 
给定一个非负整数 c ，你要判断是否存在两个整数 a 和 b，使得 a^2 + b^2 = c。
## 代码实现
```c
class Solution {
public:
    bool judgeSquareSum(int c) {
        int left,right,sum;
        left=0;right=sqrt(c);
          while(left <= right){
        sum=left*left+right*right;
        if(sum == c) return true;
        if(sum>c){right--;}
        else left++;}
        return false;
    }
};
```
## 总结：
首先考虑采用两个for循环，然后发现超时。其次采用两个指针的方式，当 left 小于等于 right的情况下：sum = left * left + right * right。如果 sum 大于 c 的话，说明 需要更小的right--；如果 sum 小于 c 的话，说明 需要更大的，left++；如果 sum 等于 c，返回 true。