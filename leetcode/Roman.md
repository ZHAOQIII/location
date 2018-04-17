## 问题分析： 
给定一个罗马数字，将其转换成整数。

返回的结果要求在 1 到 3999 的范围内。


## 代码实现
```c
class Solution {
public:
    int romanToInt(string s) {   
        int res = 0;
        unordered_map<char, int> m{{'I', 1}, {'V', 5}, {'X', 10}, {'L', 50}, {'C', 100}, {'D', 500}, {'M', 1000}};
        for (int i = 0; i < s.size(); ++i) {
            int val = m[s[i]];
            if (i == s.size() - 1 || m[s[i+1]] <= m[s[i]]) res += val;
            else res -= val;
        }
        return res;
    }
        
    };
```
## 总结：
将罗马数字的字母转化为对应的整数值，如果当前数字是最后一个数字，或者之后的数字比它小的话，则加上当前数字，否则就减去这个数字。