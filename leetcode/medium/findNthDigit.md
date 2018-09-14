## 问题分析：
在无限的整数序列 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, ...中找到第 n 个数字。
```c
class Solution {
public:
    int findNthDigit(int n) {
    long digit = 1, ith = 1, base = 9;
        while(n > base*digit)
        {
            n -= base*(digit++);
            ith += base;
            base *= 10;
        }
        return to_string(ith+(n-1)/digit)[(n-1)%digit]-'0';
    }
};
```
## 总结：
一位有９个数字，二位数有90个数字，三位数有900个数，依次类推．因此可以每次增加一位数字，看n是否还在这个范围内．
