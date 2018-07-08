## 问题分析： 

给定一个二叉树，它的每个结点都存放着一个整数值。

找出路径和等于给定数值的路径总数。

路径不需要从根节点开始，也不需要在叶子节点结束，但是路径方向必须是向下的（只能从父节点到子节点）。

二叉树不超过1000个节点，且节点数值范围是 [-1000000,1000000] 的整数。

## 代码实现
```c
class Solution {
public:
    int pathSum(TreeNode* root, int sum) {
            if(root == nullptr)
            return 0;
        return dfs(root, sum)+pathSum(root->left, sum)+pathSum(root->right, sum);
    }

    private: int dfs(TreeNode *root, int sum){
        int res = 0;
        if(root == nullptr)
            return res;
        if(sum == root->val)
            res++;
        res+=dfs(root->left,sum - root->val);
        res+=dfs(root->right,sum - root->val);
        return res;   
    }
};
```
## 总结：
1.先判断是否为空二叉树；  
2.如果不是，从根节点向左右子树遍历，找到等于sum的路径；  
3.如果找不到，以根节点下的左右子树作为新的节点，遍历，以此类推，直到找到和为sum的路径；