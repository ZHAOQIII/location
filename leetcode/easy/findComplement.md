## 问题分析： 
给定一个正整数，输出它的补数。补数是对该数的二进制表示取反。
## 代码实现
```c
class Solution {
public:
    int findComplement(int num) {
     int tem=num;
        int cou=1;
        while(tem!=0){
            tem=tem>>1;
            cou=cou<<1;
        }
        return (cou-1) ^ num;    
    }
};
```
## 总结：
从最高位的1开始向后按位取反。左移运算符(<<)，左移运算将一个位串信息向左移指定的位，右端空出的位用0补充。右移运算符(>>)，右移运算将一个位串信息向右移指定的位，右端移出的位的信息被丢弃。然后将给定数字和一个特定的掩码进行XOR操作(异或操作)。