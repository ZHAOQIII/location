## 问题分析： 
给定两个字符串形式的非负整数 num1 和num2 ，计算它们的和。

## 代码实现
```c
class Solution {
public:
    string addStrings(string num1, string num2) {
        string res = "";
        int m = num1.size() - 1, n = num2.size() - 1, carry = 0;
        while(m >= 0 || n >= 0){
            int a = m >= 0 ? num1[m --] - '0' : 0;
            int b = n >= 0 ? num2[n --] - '0' : 0;
            int sum = a + b + carry;
            res.insert(res.begin(), sum% 10 + '0');
            carry = sum/ 10;
        }
        return carry ? "1" + res : res;
    }
};
```
## 总结：
先将num1和num2逆序相加，然后判断是否有进位，如果有，则下一位加上进位。