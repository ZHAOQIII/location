## 问题分析： 
给定两个整数 L 和 R ，找到闭区间 [L, R] 范围内，计算置位位数为质数的整数个数。

（注意，计算置位代表二进制表示中1的个数。例如 21 的二进制表示 10101 有 3 个计算置位。还有，1 不是质数。）
## 代码实现
```c
class Solution {
public:
    int countPrimeSetBits(int L, int R) {
              int count = 0;
        for(int x = L; x <= R; x++)
        {
            bitset<32> bits(x);
            int n = bits.count();
            if(n == 2 || n == 3 || n == 5 || n == 7 || n == 11 || n == 13 || n == 17 || n == 19) count++;
        }
        return count;
    }
};
```
## 总结：
依次遍历闭区间中的数，首先将其转化为二进制，然后统计其中1的个数，判断个数是否属于质数，属于则统计数加1。
      
      
      