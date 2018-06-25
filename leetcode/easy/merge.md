## 问题分析： 
给定两个有序整数数组 nums1 和 nums2，将 nums2 合并到 nums1 中，使得 num1 成为一个有序数组。


## 代码实现
```c
class Solution {
public:
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        m--;
        n--;
        while(m>=0 && n>=0){
            if(nums1[m]>nums2[n]){
                nums1[m+n+1] = nums1[m];
                m--;
            }else{
                nums1[m+n+1] = nums2[n];
                n--;
            }
        }
        while(n>=0){
            nums1[n] = nums2[n];
            n--;
        }
    }
};
```
## 总结：
因为两个数组为有序数组，所以可以逆序比较，较大者放于新数组的末位，再比较较大者数组的倒数第二位与另一数组的最后一位比较，再将较大者放于新数组的倒数第二位，以此类推。