## 问题分析： 
给定一个字符串，验证它是否是回文串，只考虑字母和数字字符，可以忽略字母的大小写。


## 代码实现
```c
class Solution {
public:
    bool isPalindrome(string s) {
     string a, b;  
        for(int i = 0 ; i < s.length() ; i ++) {  
            if((s[i] >= 'a'&&s[i] <= 'z')||(s[i] >= '0'&&s[i] <= '9'))  {  
                a += s[i];  
                b.insert(b.begin(), s[i]);  
            }  
            if(s[i] >= 'A'&&s[i] <= 'Z') {  
                s[i] = s[i] - ('A'-'a');  
                a += s[i];  
                b.insert(b.begin(), s[i]);  
            }  
        }  
        if(a == b) return true;  
        else return false;     
    }
};
```
## 总结：
删除掉不是字母和数字的字符，把所有大写字母变为小写，然后在验证是否为回文串。