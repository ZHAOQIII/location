## 问题分析： 
给定一个正整数，返回它在 Excel 表中相对应的列名称。

## 代码实现
```c
class Solution {
public:
    string convertToTitle(int n) {
     string res="";
        while(n)
        {
            res=char((n-1)%26+'A')+res;
            n=(n-1)/26;
        }
        return res;    
    }
};
```
## 总结：
26个字母为一个周期，除26取余即可。