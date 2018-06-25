## 问题分析： 
给定一个整数 (32位有符整数型)，请写出一个函数来检验它是否是4的幂。


## 代码实现
```c
class Solution {
public:
    bool isPowerOfFour(int num) {
  if (n <= 0)
        return false;
    while (n > 1)
    {
        if (n % 4 == 0)
            n = n / 4;
        else
            return false;
    }
    return true;
        
    }
};

```
## 总结：
当num大于1时，首先判断除以4以后的余数是否等于0，然后判断商是否大于大于1。