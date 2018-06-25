## 问题分析： 
给定一个整数，写一个函数来判断它是否是 3 的幂次方。


## 代码实现
```c
class Solution {
public:
    bool isPowerOfThree(int n) {
  if (n <= 0)
        return false;
    while (n > 1)
    {
        if (n % 3 == 0)
            n = n / 3;
        else
            return false;
    }
    return true;
        
    }
};

```
## 总结：
当num大于1时，首先判断除以3以后的余数是否等于0，然后判断商是否大于大于1。