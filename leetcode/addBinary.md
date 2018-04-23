## 问题分析： 
给定两个二进制字符串，返回他们的和（用二进制表示）。

输入为非空字符串且只包含数字 1 和 0。


## 代码实现
```c
class Solution {
public:
    string addBinary(string a, string b) {
      string s="";
        int c=0;
        int i=a.size()-1;
        int j=b.size()-1;
        while(i>=0||j>=0||c==1)
        {
            c+=i>=0?a[i--]-'0':0;
            c+=j>=0?b[j--]-'0':0;
            s=char(c%2+'0')+s;
            c/=2;
        }
        return s;
    }
};
```
## 总结：
从后往前遍历，先从最低位开始，将字符串a赋给c，再加上字符串b的值，再将c的值赋给字符串s，如果有进位，则下一次遍历时c=1，否则等于0。