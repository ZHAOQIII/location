## 问题分析： 
自除数 是指可以被它包含的每一位数除尽的数。

例如，128 是一个自除数，因为 128 % 1 == 0，128 % 2 == 0，128 % 8 == 0。

还有，自除数不允许包含 0 。

给定上边界和下边界数字，输出一个列表，列表的元素是边界（含边界）内所有的自除数。
## 代码实现
```c
class Solution {
public:
  vector<int> selfDividingNumbers(int left, int right) {
    vector<int> ret;
    int mod, temp;
    for (int i = left; i <= right; ++i) {
      temp = i;
      while(temp) {
        if (!(mod = temp % 10) || (i % mod)) { break; }
        temp = temp / 10;
      }
      if (!temp) { ret.push_back(i); }
    }
    return ret;
  }
};
```
## 总结：
要判断一个数是不是可自分的，看该数字是不是可整除数字上的每一位，从左界限开始，逐个判断是不是可自分数，直到右界限。
      
      
      