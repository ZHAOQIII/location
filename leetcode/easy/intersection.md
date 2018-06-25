## 问题分析： 
给定两个数组，写一个函数来计算它们的交集。


## 代码实现
```c
class Solution {
    private:vector<int>result;
public:
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {
        set<int> s1(nums1.begin(),nums1.end());
        for(int i=0;i<nums2.size();i++)
        {
            if(s1.erase(nums2[i]))
            result.push_back(nums2[i]);
        }
        return result;
    }
};
```
## 总结：
将nums1数据装入s1中，如果s1中含有nums2{i}，那么push到result中，并且把这个数从s1中删去，避免下一次处理到重复的数，最后返回的值即是交集。