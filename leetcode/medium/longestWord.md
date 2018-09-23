## 问题分析：
给出一个字符串数组words组成的一本英语词典。从中找出最长的一个单词，该单词是由words词典中其他单词逐步添加一个字母组成。若其中有多个可行的答案，则返回答案中字典序最小的单词。

若无答案，则返回空字符串。
## 代码实现
```c
class Solution {
public:
    string longestWord(vector<string>& words) {
        sort(words.begin(), words.end());
        unordered_set<string> built;
        string res;
        for (string w : words) {
            if (w.size() == 1 || built.count(w.substr(0, w.size() - 1))) {
                res = w.size() > res.size() ? w : res;
                built.insert(w);
            }
        }
        return res;
    }
};
```
## 总结：
首先将vector进行了排序。vector储存的是string。那么，这里使用sort函数排序，应该首先按照字符串长度从短到长排序，相同长度的字符串，根据字典顺序排序。那么这样处理之后，题目要找的答案应该就是排在后面的。
那么，从前往后遍历，如果当前字符串长度等于1.那么就直接将res更新为当前字符串。并且将当前字符串插入到built中。如果遇到后面的字符串，如果长度减一的字符串在built中有对应项。那么这时候就应该对res进行更新。
