## 问题分析： 
给出 N 名运动员的成绩，找出他们的相对名次并授予前三名对应的奖牌。前三名运动员将会被分别授予 “金牌”，“银牌” 和“ 铜牌”（"Gold Medal", "Silver Medal", "Bronze Medal"）。

(注：分数越高的选手，排名越靠前。)
## 代码实现
```c
class Solution {
public:
    vector<string> findRelativeRanks(vector<int>& nums) {
        vector<int> nums1=nums;
        vector<int> res(nums.size(),0);
        vector<string> res1;
        sort(nums.begin(),nums.end());
        for(int i=0;i<nums1.size();i++)
        {
            for(int j=0;j<nums.size();j++)
            {
                if(nums[j]==nums1[i])
                    res[i]=nums.size()-j;
                
            }
            if(res[i]==1)
                res1.push_back("Gold Medal");
            else if(res[i]==2)
                res1.push_back("Silver Medal");
            else if(res[i]==3)
                res1.push_back("Bronze Medal");
            else
                res1.push_back(to_string(res[i]));
        }
        return res1;
    }
};
```
## 总结：
先复制到一个新的数组中并排序，在字符串中先将前三名对应的奖牌入栈，然后再将剩余名次依次入栈。