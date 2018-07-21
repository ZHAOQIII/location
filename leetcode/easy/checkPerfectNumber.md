## 问题分析： 
对于一个 正整数，如果它和除了它自身以外的所有正因子之和相等，我们称它为“完美数”。

给定一个 正整数 n， 如果他是完美数，返回 True，否则返回 False
## 代码实现
```c
class Solution {
public:
    bool checkPerfectNumber(int num) {
     int i, sum=1;
         if(num == 1) return false;
        for(i=2;i<sqrt(num);i++){
            if(num%i==0){
                sum=sum+i;
                sum=sum+num/i;
            }
        }
        return sum==num;
    }
};
```
## 总结：
先判断是否等于1，1不是完美数。如果余数为0，则商和除数皆为正因子，所以依次遍历小于正整数开平方数的数能否被除尽，如果不能，则加1继续遍历，否则将商和除数累加后再加1继续遍历。