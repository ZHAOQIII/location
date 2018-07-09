## 问题分析： 


给定一个范围在  1 ≤ a[i] ≤ n ( n = 数组大小 ) 的 整型数组，数组中的元素一些出现了两次，另一些只出现一次。

找到所有在 [1, n] 范围之间没有出现在数组中的数字。

您能在不使用额外空间且时间复杂度为O(n)的情况下完成这个任务吗? 你可以假定返回的数组不算在额外空间内。

## 代码实现
```c

class Solution {
public:
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        vector<int> test;  
        vector<int> ans;    
        for(int i=0;i<=nums.size();i++){   
            test.push_back(0);
        }
        for(int i=0;i<nums.size();i++){
            if(!test[nums[i]]){
                test[nums[i]]++;
            }
        }
        for(int i=1;i<=nums.size();i++){ 
            if(!test[i]){
                ans.push_back(i);
            }
        }
        return ans;
    }

};
```
## 总结：
直接在原数组里改变位置的大小，由于里面的数都在1到n之间，将数组中的值作为索引，找到该索引上的值变为1，最后再统一筛选；