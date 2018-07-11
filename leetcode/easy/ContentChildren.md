## 问题分析： 
假设你是一位很棒的家长，想要给你的孩子们一些小饼干。但是，每个孩子最多只能给一块饼干。对每个孩子 i ，都有一个胃口值 gi ，这是能让孩子们满足胃口的饼干的最小尺寸；并且每块饼干 j ，都有一个尺寸 sj 。如果 sj >= gi ，我们可以将这个饼干 j 分配给孩子 i ，这个孩子会得到满足。你的目标是尽可能满足越多数量的孩子，并输出这个最大数值。

注意：

你可以假设胃口值为正。
一个小朋友最多只能拥有一块饼干。
## 代码实现
```c
class Solution {
public:
    int findContentChildren(vector<int>& g, vector<int>& s) {
      sort(g.begin(), g.end());
        sort(s.begin(), s.end());
        int j=0;
       for(int i = 0; i < s.size(); i++) {
            if(s[i] >= g[j])
                j++;  
        if(j >= g.size())
                break;}

        return j;
    }
};
```
## 总结：
可以转化为两个数组g, s。求最多有多少个s中的元素分别>=g中的元素。所以将两个数组排序后，遍历一遍比较计数即可。