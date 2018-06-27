## 问题分析： 
给定两个数组，写一个方法来计算它们的交集。

## 代码实现
```c
class Solution {
     private:vector<int>result;
public:
    vector<int> intersect(vector<int>& nums1, vector<int>& nums2) {
       sort(nums1.begin(),nums1.end());
        sort(nums2.begin(),nums2.end());
        for (int i = 0, j = 0; i < nums1.size() && j < nums2.size(); ) {
              if (nums1[i] == nums2[j])
        {
            result.push_back(nums1[i]);
            i++;
            j++;
        }
        else if (nums1[i] < nums2[j])
            i++;
        else if (nums1[i] > nums2[j])
            j++;
                 
         }
     
         return result;  
    }
};

```
## 总结：
先对两个数组排序，然后遍历数组比较大小，找到交集则把交集入栈。