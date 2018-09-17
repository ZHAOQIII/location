## 问题分析：
给定两个没有重复元素的数组 nums1 和 nums2 ，其中nums1 是 nums2 的子集。找到 nums1 中每个元素在 nums2 中的下一个比其大的值。

nums1 中数字 x 的下一个更大元素是指 x 在 nums2 中对应位置的右边的第一个比 x 大的元素。如果不存在，对应位置输出-1。

## 代码实现
```c
class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& findNums, vector<int>& nums) {
        int n=findNums.size(),m=nums.size(),k;
        vector<int>res;
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(findNums[i]==nums[j]){
                    if(j==m-1){res.push_back(-1);}
                    else {for( k=j+1;k<m;++k){
                        if(nums[k]>nums[j]){res.push_back(nums[k]);break;}

                }
                         if(k==m){res.push_back(-1);}
                }
            }
        }}
        return res;
    }
};
```
## 总结：
定位到nums中的位置，然后依次往后寻找是否存在大于当前值的数，存在则入栈该数，否则入栈-1。
