## 问题分析： 
给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的一个字母异位词。


## 代码实现
```c
class Solution {
public:
    bool isAnagram(string s, string t) {
      if(s.size() != t.size()){
            return false;
        }   
          sort(s.begin(), s.end());
        sort(t.begin(), t.end());

for(int i = 0; i < s.size(); i++){
            if(s[i] != t[i]){
                return false;
            }
        }
        return true;
    }
};
```
## 总结：
首先判断两个字符串的长度是否相等，不相等则返回false。然后将两个字符串排序，排序后的字符串如果相等则是字母异位词。