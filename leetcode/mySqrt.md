## 问题分析： 
实现 int sqrt(int x) 函数。

计算并返回 x 的平方根，其中 x 是非负整数。

由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。


## 代码实现
```c
class Solution {
public:
    int mySqrt(int x) {
        long i;
        for (i = 1; i * i <= x; i++)
            continue;
        return --i;
    }
};
```
## 总结：
从1开始逐项验证是否为x的平方根。