## 问题分析： 
给定两个字符串, A 和 B。

A 的旋转操作就是将 A 最左边的字符移动到最右边。 例如, 若 A = 'abcde'，在移动一次之后结果就是'bcdea' 。如果在若干次旋转操作之后，A 能变成B，那么返回True。
## 代码实现
```c
class Solution {
public:
    bool rotateString(string A, string B) {
        string str=A+A;
       int n,m,j;
        n=A.size();m=B.size();
        if(m==0&&n==0) return true;
        if(m!=n) return false;
        for(int i=0;i<n;i++){
            if(str[i]==B[0]){
                for(j=1;j<m;j++){
                 if(str[i+j]==B[j]) continue; 
                    else break;
                }
                if(j==m) return true;
            }
        }
        return false;
    }
};
```
## 总结：
当两个字符串长度不相等时，返回false；否则，找到B首字母在str中出现的位置，并判断后续字符是否依次相等。
      
      
      