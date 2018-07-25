## 问题分析： 
给定一个字符串来代表一个学生的出勤纪录，这个纪录仅包含以下三个字符：

1. 'A' : Absent，缺勤  
2. 'L' : Late，迟到  
3. 'P' : Present，到场  
如果一个学生的出勤纪录中不超过一个'A'(缺勤)并且不超过两个连续的'L'(迟到),那么这个学生会被奖赏。

你需要根据这个学生的出勤纪录判断他是否会被奖赏。
## 代码实现
```c
class Solution {
public:
    bool checkRecord(string s) {
        int n=s.size(),a=0;
        for(int i=0;i<n;i++) {           
            if(s[i]=='A') a++;
            else if(s[i]=='L'&&s[i+1]=='L'&&s[i+2]=='L') return false;
        }
        if(a<=1) {return true;}
        return false;
    }
};
```
## 总结：
首先判断是否有连续的三个‘L’，如果有，则返回false，与此同时统计字符串中‘A’的数目。如果‘A’的数目小于等于1，则返回true。