## 问题分析： 
给定一个偶数长度的数组，其中不同的数字代表着不同种类的糖果，每一个数字代表一个糖果。你需要把这些糖果平均分给一个弟弟和一个妹妹。返回妹妹可以获得的最大糖果的种类数。
## 代码实现
```c
class Solution {
public:
    int distributeCandies(vector<int>& candies) {
        int n=candies.size(),sum=0,m;
        m=n/2;
        sort(candies.begin(),candies.end());
          if(n<1) return 0;
        if(n==2) return 1;
        for(int i=0;i<n;i++){
            if(candies[i]!=candies[i+1]){sum++;}
        }
        if(sum>m){return m;}
        return sum;
    }
};
```
## 总结：
因为要平均分配，所以妹妹最多能拿到n/2种糖果。当糖的种类大于n/2时，妹妹最多能拿到n/2种糖果；当糖的种类小于n/2时，妹妹最多能拿到糖的种类为糖的种类。