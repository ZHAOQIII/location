## 问题分析： 
集合 S 包含从1到 n 的整数。不幸的是，因为数据错误，导致集合里面某一个元素复制了成了集合里面的另外一个元素的值，导致集合丢失了一个整数并且有一个元素重复。

给定一个数组 nums 代表了集合 S 发生错误后的结果。你的任务是首先寻找到重复出现的整数，再找到丢失的整数，将它们以数组的形式返回。
## 代码实现
```c
class Solution {
public:
    vector<int> findErrorNums(vector<int>& nums) {
        vector<int> s(2);
        map<int,int> p;
        for(int j=1;j<=nums.size();j++)  p[j]=0;
        for(int i=0;i<nums.size();i++)  p[nums[i]]++;
        for(int k=1;k<=nums.size();k++){
            if(p[k]==2)  s[0]=k;
            else if(p[k]==0)  s[1]=k;
        }
        return s;
    }
};
```
## 总结：
定义一个新的数组用来存放重复出现的整数和丢失的整数，统计数组中的数值的次数，次数为0的则为丢失的整数，出现次数为2的则为重复出现的整数。