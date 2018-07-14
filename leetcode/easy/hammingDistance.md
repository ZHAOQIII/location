## 问题分析： 
两个整数之间的汉明距离指的是这两个数字对应二进制位不同的位置的数目。

给出两个整数 x 和 y，计算它们之间的汉明距离。
## 代码实现
```c
class Solution {
public:
    int hammingDistance(int x, int y) {
      int hammingDistance = 0;
        int z = x ^ y;
    while(z!=0){
            hammingDistance++; 
            z = z & (z - 1);
        }
        return hammingDistance;  
    }
};
```
## 总结：
先将z=x^y按位异或，则z上值为1的位数即是汉明距离。