## 问题分析： 
给定一个整数，将其转化为7进制，并以字符串形式输出。
## 代码实现
```c
class Solution {
public:
    string convertToBase7(int num) {
        
        string res = "";
        if(num == 0) return "0";
        
        bool key = num >= 0 ? true : false;
        num = abs(num);
        
        while(num > 0){
            res = to_string(num%7) + res;
            num = num/7;
        }
        if(!key) res = '-'+res;
        return res;
    }
};
```
## 总结：
取余数加入到res的前面，除以7，直到小于7，最后再把num加入result的前面。