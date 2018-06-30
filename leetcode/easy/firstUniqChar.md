## 问题分析： 
给定一个字符串，找到它的第一个不重复的字符，并返回它的索引。如果不存在，则返回 -1。

## 代码实现
```c
class Solution {
public:
    int firstUniqChar(string s) {
        vector<int>count(26);
        for (int i = 0; i < (int)s.size(); i++)
        {
            count[s[i] - 'a'] ++;
        }
        for (int i = 0; i < (int)s.size(); i++)
        {
            if (count[s[i] - 'a'] == 1)
                return i;
        }
        return -1;
  
    }
};

```
## 总结：
先对字符串的各个字符进行计数，找出个数等于1的字符所在位置，否则返回-1。