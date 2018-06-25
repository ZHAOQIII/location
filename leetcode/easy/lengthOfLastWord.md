## 问题分析： 
给定一个仅包含大小写字母和空格 ' ' 的字符串，返回其最后一个单词的长度。

如果不存在最后一个单词，请返回 0 。


## 代码实现
```c
int lengthOfLastWord(char* s) {
   int n = strlen(s);  
        int p = 0;  
        for(int i = n-1;i > -1;--i){  
            if(s[i] != ' '){  
                p = i-1;  
                while(s[p] != ' ' && p > -1) p--;  
                return i-p;  
            }  
        }  
        return 0;  
} 
```
## 总结：
从后往前遍历，当遇到空格时，保留当前值，返回字符串长度减去当前值即是最后单词的长度。