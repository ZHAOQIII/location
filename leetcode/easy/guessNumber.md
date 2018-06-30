## 问题分析： 
我们正在玩一个猜数字游戏。 游戏规则如下：  
我从 1 到 n 选择一个数字。 你需要猜我选择了哪个数字。  
每次你猜错了，我会告诉你这个数字是大了还是小了。
你调用一个预先定义好的接口 guess(int num)，它会返回 3 个可能的结果（-1，1 或 0）：  
-1 : 我的数字比较小  
 1 : 我的数字比较大  
 0 : 恭喜！你猜对了！

## 代码实现
```c
class Solution {
public:
    int guessNumber(int n) {
        int low,high,mid;
        low=1;high=n;
        while(low<=high){
        mid=low+(high-low)/2;
        if(guess(mid)==1){low=mid+1;}
        else {high=mid-1;}
    }
        return low;
    }
    
};

```
## 总结：
采用二分法选取数据去比较，如果得到-1，则选取的数据较小，则将范围缩小到所有数据较小的一半，如果得到1，则缩小到较大的一半，否则直接返回当前值。