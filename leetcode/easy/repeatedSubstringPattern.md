## 问题分析： 
给定一个非空的字符串，判断它是否可以由它的一个子串重复多次构成。给定的字符串只含有小写英文字母，并且长度不超过10000。
## 代码实现
```c
class Solution {
public:
    bool repeatedSubstringPattern(string s) {
           int m=s.size();
        for(int p=1;p<m/2+1;p++)
            for(int i=0;i<m-p;i++)
            {
                if(s[i]!=s[i+p]) break;
                if(m%p==0&&i==m-p-1) return true;
            }
         return false;
    }
};
```
## 总结：
假设子串长度为p,那么原串s的长度为n*p(n>=2),那么s数组，由于对称性会在下标p+1起开始逐一递增。直到增加到m-p,如果[m]%p==0代表s由整数个长度为p的子串构成。。