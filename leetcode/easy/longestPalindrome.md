## 问题分析： 

给定一个包含大写字母和小写字母的字符串，找到通过这些字母构造成的最长的回文串。

在构造过程中，请注意区分大小写。比如 "Aa" 不能当做一个回文字符串。

## 代码实现
```c
class Solution {
public:
    int longestPalindrome(string s) {
        int odds = 0;
        for (auto c = 'A'; c <= 'z'; ++c) {
            odds += count(s.cbegin(), s.cend(), c) & 1;
        }
        return s.length() - odds + (odds > 0);
    }
};

```
## 总结：
回文有两种形式，一种是左右完全对称，还有一种是以中间字符为中心，左右对称，统计出所有偶数个字符的出现总和，如果有奇数个字符的话，最后结果再加1。。