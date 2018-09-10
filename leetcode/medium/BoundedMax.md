## 问题分析：
给定一个元素都是正整数的数组A ，正整数 L 以及 R (L <= R)。

求连续、非空且其中最大元素满足大于等于L 小于等于R的子数组个数。## 代码实现
```c
class Solution {
public:
    int numSubarrayBoundedMax(vector<int>& A, int L, int R) {
         int len = A.size();
        int ans = 0;
        int left = -1;
        int right = -1;
        for(int i=0; i<len; i++) {
            if(A[i] > R) {
                left = i;
                right = i;
            }
            else if(A[i]<L) {
                ans += (i-left)-(i-right);
            }
            else {
                ans += (i-left);
                right = i;
            }
        }
        return ans;
    }
};  ```
## 总结：
遍历数组，通过A[i]大小判断：若 A[i] 在L、R之间，则 ans+=(i-j)；若 A[i] 大于R，则更改左界 left=i；
关键在于处理小于L的情况，由于需要子数组的最大值在L、R之间，单纯的 A[i]不能算，需要知道最近合法的数字，即右界。
