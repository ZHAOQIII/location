## 问题分析：
给定一个正整数 N，试求有多少组连续正整数满足所有数字之和为 N?
## 代码实现
```c
class Solution {
public:
    int consecutiveNumbersSum(int N) {
       int cnt = 0;
        for (int i = 1; i <= N; i++) {
            int a = i*(i - 1) / 2;
            if (a >= N)break;
            int num = N - a;
            if (num%i == 0)cnt++;
        }
        return cnt;
    }
};
```
## 总结：
等差数列求和公式Sn=n*(n-1)/2+a*n计算，查找a是否存在.
