## 问题分析： 

给定两个字符串 s 和 t，它们只包含小写字母。

字符串 t 由字符串 s 随机重排，然后在随机位置添加一个字母。

请找出在 t 中被添加的字母。

## 代码实现
```c
class Solution {
public:
    char findTheDifference(string s, string t) {
 sort(s.begin(),s.end());
        sort(t.begin(),t.end());
        int i=0;
        while(s[i]==t[i]){
            i++;
        }
        return t[i];
    }
};

```
## 总结：
先将两个字符串排序，然后比较两个字符串，如果相等则比较下一位，否则返回当前值。