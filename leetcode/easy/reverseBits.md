## 问题分析： 
颠倒给定的 32 位无符号整数的二进制位。


## 代码实现
```c
class Solution {
public:
    uint32_t reverseBits(uint32_t n) {
        int i;  
        uint32_t res=0;  
        for(i=0;i<32;i++)  
        {  
            res=(res<<1)^(n&1);    //res左移一位，腾出最后一位放n的当前的最后一位
            n>>=1;  
        }  
        return res;  
    }
};
```
## 总结：
res左移一位，腾出最后一位放n的当前的最后一位，然后再将n右移一位，依次循环，将n颠倒。