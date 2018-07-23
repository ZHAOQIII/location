## 问题分析： 
给定一个字符串和一个整数 k，你需要对从字符串开头算起的每个 2k 个字符的前k个字符进行反转。如果剩余少于 k 个字符，则将剩余的所有全部反转。如果有小于 2k 但大于或等于 k 个字符，则反转前 k 个字符，并将剩余的字符保持原样。
## 代码实现
```c
class Solution {
public:
    string reverseStr(string s, int k) {
        if(s.size()<k){
                reverse(s.begin(),s.end());
            return s;
        }
       for(int i=0;i<s.size(); ){
            if(s.size()-i<k){
                reverse(s.begin()+i,s.begin()+s.size());
                return s;
            }     
            reverse(s.begin()+i,s.begin()+i+k);
            i+=k*2;
        }
        return s;
    }
};
```
## 总结：
如果字符长度少于 k 个字符，则反转全部字符串。如果字符长度大于2k，每2k个字符的前k个字符进行反转，依次翻转，直到字符串结束。