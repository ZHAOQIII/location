## 问题分析： 
实现 strStr() 函数。

给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。


## 代码实现
```c
class Solution {
public:
    int strStr(string haystack, string needle) {
        if (needle=="")
            return 0;
        int m=haystack.size();
        int n=needle.size();
        if(m<n){
            return -1;
        }
        for(int i=0;i<m-n+1;i++){
            int j=0;
            for(j=0;j<n;j++){
                if(haystack[i+j]!=needle[j]){
                    break;
                }              
             }
            if(j==n){
                return i;
            }       
        }
        return -1;
    }
};
```
## 总结：
先比较两个字符串的大小如果needle大于haystack，则返回-1,。否则用needle中的字符遍历haystack。