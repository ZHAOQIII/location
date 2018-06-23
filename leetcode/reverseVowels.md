## 问题分析： 

编写一个函数，以字符串作为输入，反转该字符串中的元音字母。

## 代码实现
```c
class Solution {
public:
    string reverseVowels(string s) {
    string vowel="aeiouAEIOU";
        int i=0,j=s.size()-1;
        while(i<j)
        {
            i=s.find_first_of(vowel,i);
            j=s.find_last_of(vowel,j);
            if(i>=j)
                break;
            swap(s[i],s[j]);
            i++;
            j--;
        }
        return s;
    }
};
```
## 总结：
利用字符串查找函数string.find()或者string.find_first_of()。