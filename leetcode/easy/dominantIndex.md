## 问题分析： 
在一个给定的数组nums中，总是存在一个最大元素 。

查找数组中的最大元素是否至少是数组中每个其他数字的两倍。

如果是，则返回最大元素的索引，否则返回-1。
## 代码实现
```c
class Solution {
public:
    int dominantIndex(vector<int>& nums) {
        vector<int>nums1=nums;
      sort(nums1.begin(),nums1.end());
        int n=nums.size(),temp,temp1,index;
        temp=nums1[n-1];
        temp1=nums1[n-2];
        for(int i=0;i<n;i++){
            if(nums[i]==temp){index=i;}
        }
        if(temp1==0){return index;}
        else {if(temp/temp1>=2) {return index;}}
        return -1;
    }
};
```
## 总结：
首先找出最大值和最大值所在的索引，然后将数组排序，只要最大值除以第二大值的商大于2，则其余皆满足条件。特殊需考虑除数为0的情况，默认最大元素至少是该元素的两倍。
      
      
      