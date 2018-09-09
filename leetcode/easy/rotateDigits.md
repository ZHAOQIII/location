如果一个数的每位数字被旋转以后仍然还是一个数字， 则这个数是有效的。0, 1, 和 8 被旋转后仍然是它们自己；2 和 5 可以互相旋转成对方；6 和 9 同理，除了这些以外其他的数字旋转以后都不再是有效的数字。

现在我们有一个正整数 N, 计算从 1 到 N 中有多少个数 X 是好数？
## 代码实现
```c
class Solution {
public:
    int rotatedDigits(int N) {
     int num = 0;
        for (int i=0; i<=N; i++) {
            num += isValid(i) ? 1 : 0;
        }
        return num;
    }

    bool isValid(int n) {
        bool flag = false;
        while (n > 0) {
            switch (n % 10) {
                case 3: case 4: case 7: return false;
                case 1: case 0: case 8: break;
                default: flag = true;
            }
            n /= 10;
        }
        return flag;
    }
};
```
依次遍历找出1——N中余数等于2，5,6，9的个数。
