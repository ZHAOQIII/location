## 问题分析： 
统计字符串中的单词个数，这里的单词指的是连续的不是空格的字符。

请注意，你可以假定字符串里不包括任何不可打印的字符。

## 代码实现
```c
class Solution {
public:
    int countSegments(string s) {
      int ret = 0;
        bool flag = false;
        for (auto i : s) {
            if (!flag && i != ' ') {
                ret++;
                flag = true;
            }
            if (flag && i == ' ')
                flag = false;
        }
        return ret;
        
    }
};
```
## 总结：
先判断是否为空格或者标点，当为单词时，进行累加，直到出现空格或标点，然后找出累加的最大值。