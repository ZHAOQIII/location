## 问题分析： 
给定一个字符串 s，计算具有相同数量0和1的非空(连续)子字符串的数量，并且这些子字符串中的所有0和所有1都是组合在一起的。

重复出现的子串要计算它们出现的次数。
## 代码实现
```c
class Solution {
public:
    int countBinarySubstrings(string s) {
     vector<int> rec;
        int count = 1;
        for(int i=1, n=s.size(); i<=n; ++i){
            if(s[i] == s[i-1]){
                ++count;
            }else{
                rec.push_back(count);
                count = 1;
            }
        }
        int res = 0;
        for(int i=1, n=rec.size(); i<n; ++i){
            res += min(rec[i-1], rec[i]);
        }
        return res;
    }
};
```
## 总结
统计连续出现相等字符的次数入栈，然后两两比较，取较小值即可。
      