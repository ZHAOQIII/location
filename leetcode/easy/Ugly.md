## 问题分析： 
编写一个程序判断给定的数是否为丑数。

丑数就是只包含质因数 2, 3, 5 的正整数。


## 代码实现
```c
class Solution {
public:
    bool isUgly(int num) {
   if(num==0) return false;
        if(num==1) return true;
        if(num%2==0){
            num=num/2;
            return isUgly(num);
        }
        if(num%3==0){
            num=num/3;
            return isUgly(num);
        }
        if(num%5==0){
            num=num/5;
            return isUgly(num);
        }
        return false;  
    }
};
```
## 总结：
当num大于1时，判断num是否能被2或3或5整除，然后进行递归判断是否只包含质因数2,3,5。