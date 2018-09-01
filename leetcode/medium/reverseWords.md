## 问题分析： 
给定一个字符串，你需要反转字符串中每个单词的字符顺序，同时仍保留空格和单词的初始顺序。
## 代码实现
```c
class Solution {
public:
    string reverseWords(string s) {
     string result = "";
        stack<char> word;
        int flag = 0;
        for (int i = 0; i < s.length(); i++) {
            if (s[i] != ' ') 
                word.push(s[i]);
            if (s[i] == ' ' || i == s.length() - 1) {
                if (flag == 1) result += " ";
                while (!word.empty()) {
                    result += word.top();
                    word.pop();
                    flag = 1;
                }
            }
        }
        return result;
    }
};
```
## 总结：
将每个单词放入栈中，当遇到空格或者最后一个字符的时候，说明当前栈内为一个完整的单词，那么就将栈内的单词按字符一个个出栈加入result字符串中，根据flag的值判断是否是第一个单词，如果不是第一个单词就要在result的后面加一个空格。
      
      