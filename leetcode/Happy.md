## 问题分析： 
编写一个算法来判断一个数是不是“快乐数”。

一个“快乐数”定义为：对于一个正整数，每一次将该数替换为它每个位置上的数字的平方和，然后重复这个过程直到这个数变为 1，也可能是无限循环但始终变不到 1。如果可以变为 1，那么这个数就是快乐数。


## 代码实现
```c
class Solution {
public:
    bool isHappy(int n) {
  int temp = n;
        while (true) {
            temp = getNext(temp);
            if (temp > 243) {
                continue;
            } else if (temp == 4 || temp == 16 || temp == 37 || temp == 58 ||
                temp == 89 || temp == 145 || temp == 42 || temp == 20) {
                return false;
            } else if (temp == 1) {
                return true;
            }
        }
    } 
    private: int getNext(int num) {
        int result = 0;
        while (num > 0) {
            result += (num % 10) * (num % 10);
            num = num / 10;
        }
        return result;
    }
};
```
## 总结：
快乐数的两个特征：

1、如果一个数“不快乐”，则它计算到后面必然陷入到这个循环里：4, 16, 37, 58, 89, 145, 42, 20, 4, ...

2、对于一个大于243的数字来说，它的下一个数字一定比它小。这是因为一个大于1000的数字，它的下一个数字一定比它小，而对于1000以下最大的数字999，它的下一个数字是243，所以1000以下数字的下一个数字也只可能小于或等于243。