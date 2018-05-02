## 问题分析： 
将一个按照升序排列的有序数组，转换为一棵高度平衡二叉搜索树。


## 代码实现
```c
class Solution {
public:
    TreeNode* sortedArrayToBST(vector<int>& nums) {
        int n=nums.size();
        if(n==0||nums.empty())
        {
            return nullptr;
        }
        if(n==1)
        {
            return new TreeNode(nums[0]);
        }
        int mid=n/2;
        vector<int> left(nums.begin(),nums.begin()+mid);
        vector<int> right(nums.begin()+mid+1,nums.end());
        TreeNode* root=new TreeNode(nums[mid]);
        root->left=sortedArrayToBST(left);
        root->right=sortedArrayToBST(right);
        return root;
    }
};
```
## 总结：
采用二分法来创建平衡二叉树，根结点刚好为数组中间的节点，根节点的左子树的根是数组左边部分的中间节点，根节点的右子树是数据右边部分的中间节点。