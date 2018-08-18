## 问题分析： 
给定一个字符串 S 和一个字符 C。返回一个代表字符串 S 中每个字符到字符串 S 中的字符 C 的最短距离的数组。
## 代码实现
```c
class Solution {
public:
    vector<int> shortestToChar(string S, char C) {
        vector<int>res;
         vector<int>res1;
      int n=S.size(),min1,min2,min,i,k;
        min1=min2=n;
        for(i=0;i<n;i++){
            if(S[i]==C){res.push_back(i);}
        }
        for(int j=0;j<n;j++){
            min=abs(res[0]-j);
            for(k=0;k<res.size();k++){
           min1=abs(res[k]-j);
           if(min1<min){min=min1;}     
        }
           res1.push_back(min);
        }
        return res1;
    }
};
```
## 总结：
先将字符串中C的位置入栈到res中，然后再将S中的字符位置逐一与res中的位置信息比较，寻找最小值依次入栈到res1。
      
      
      