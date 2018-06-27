## 问题分析： 
给定一个正整数 num，编写一个函数，如果 num 是一个完全平方数，则返回 True，否则返回 False。

## 代码实现
```c
class Solution {
public:
    bool isPerfectSquare(int num) {
     for (int i = 1; i <= num / i; ++i) {
            if (i * i == num) return true;
        }
        return false;  
    }
};
```
## 总结：
完全平方数是由两个相同的数相乘得来的，从1开始遍历，如果能找到的这两个数，则为完全平方数。