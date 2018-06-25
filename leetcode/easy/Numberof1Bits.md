## 问题分析： 

编写一个函数，输入是一个无符号整数，返回其二进制表达式中数字位数为 ‘1’ 的个数（也被称为汉明重量）。


## 代码实现
```c
class Solution {
public:
    int hammingWeight(uint32_t n) {
        int count = 0;
        while(n!=0){
            if(n&0x1 == 1){
                count ++;
            }
            n = n>>1;
        }
        
        return count;
    }
};
```
## 总结：
直接移位即可，右移32次，每次判断最后一位是否为1即可。