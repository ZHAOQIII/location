## 问题分析： 
统计所有小于非负整数 n 的质数的数量。

## 代码实现
```c
class Solution {
public:
    int countPrimes(int n) {
        if (n <= 2) return 0;
        else if (n <= 3) return 1;
        else{
            int count = 1;
            for (int i = 3; i < n; i ++){
                if (i % 2 == 0) continue;
                int j = 2;
                for (; j * j <= i; j ++){
                    if(i % j == 0) break;
                }
                if (j * j > i) count ++;
            }
            return count;
        }
    }
};
```
## 总结：
1既不是素数也不是合数。2是最小的素数。所以从2開始遍历，假设这个元素没有被处理，那么将素数的个数加1，然后将2*2,2*3,2*4……2* k（ 2* k < n）标记为已经被处理了的。接着開始处理3，同理将3*2,3*3,3*4…..3*m( 3 * m < n)标记为已被处理了的，接着是4，因为这个元素已经被处理。继续向后遍历。