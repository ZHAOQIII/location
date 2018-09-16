## 问题分析：
给定一个按照升序排列的整数数组 nums，和一个目标值 target。找出给定目标值在数组中的开始位置和结束位置。

你的算法时间复杂度必须是 O(log n) 级别。

如果数组中不存在目标值，返回 [-1, -1]。
## 代码实现
```c
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        vector<int>res;
                vector<int>res1;

        int n=nums.size(),m;
        for(int i=0;i<n;i++){
            if(nums[i]==target){res.push_back(i);}
        }
        m=res.size();
        if(m==0){res1.push_back(-1);res1.push_back(-1);}
        if(m==1){res1.push_back(res[0]);res1.push_back(res[0]);}
        if(m>=2){res1.push_back(res[0]);res1.push_back(res[m-1]);}
        return res1;
    }
};
```
## 总结：
找到等于目标值的位置，入栈。然后再判断是否存在目标值或者存在几个目标值。
