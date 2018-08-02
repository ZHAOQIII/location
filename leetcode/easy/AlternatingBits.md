## 问题分析： 
给定一个正整数，检查他是否为交替位二进制数：换句话说，就是他的二进制数相邻的两个位数永不相等。
## 代码实现
```c
class Solution {
public:
    bool hasAlternatingBits(int n) {
           vector<int>bits;
    while(n>0)
    {
      bits.push_back(n%2);
      n/=2;
    }  
        for(int i=0;i<bits.size();i++){
            if(bits[i]==bits[i+1]){return false;}
        }
        return true;
    }
};
```
## 总结：
先将正整数变成二进制数，然后再判断数组是否存在前后两个数值相等，如果存在，就返回false，否则返回true。