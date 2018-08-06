## 问题分析： 
有两种特殊字符。第一种字符可以用一比特0来表示。第二种字符可以用两比特(10 或 11)来表示。

现给一个由若干比特组成的字符串。问最后一个字符是否必定为一个一比特字符。给定的字符串总是由0结束。
## 代码实现
```c
class Solution {
public:
    bool isOneBitCharacter(vector<int>& bits) {
       int n=bits.size(),i=0; 
        if(bits[n-2]==0){return true;}
        else{while(i<n-1){
           i=bits[i]+1+i;
        }}
       return i==n-1;; 
    }
};
```
## 总结：
倒数第二位为0的字符串，一定是满足条件的。依次从头遍历字符串，当面对1时，i=i+2,，因为后面一位不管是0或1，都组成2比特，否则i++；
      
      
      