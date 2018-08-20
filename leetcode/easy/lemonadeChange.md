## 问题分析： 
在柠檬水摊上，每一杯柠檬水的售价为 5 美元。

顾客排队购买你的产品，（按账单 bills 支付的顺序）一次购买一杯。

每位顾客只买一杯柠檬水，然后向你付 5 美元、10 美元或 20 美元。你必须给每个顾客正确找零，也就是说净交易是每位顾客向你支付 5 美元。

注意，一开始你手头没有任何零钱。

如果你能给每位顾客正确找零，返回 true ，否则返回 false 。

 
## 代码实现
```c
class Solution {
public:
    bool lemonadeChange(vector<int>& bills) {
      int s1,s2,n=bills.size(),i;
        s1=s2=0;
        if(bills[0]>5) return false;
        for(i=0;i<n;i++){
          if(bills[i]==5){s1++;}  
           if(bills[i]==10){s1--;s2++;if(s1<0) return false;} 
              if(bills[i]==20){
                  if(s1>=1&&s2>=1) {s1--;s2--;}
                  else if(s1>=3) {s1=s1-3;}
                  else return false;
                 
        }}
        return true;
    }
};
```
## 总结：
根据题意，可得，如果第一个顾客账单超过5元，则无法正确找零。依次遍历数组，统计5元的数量，当收到10元时，需找零5元，s1--，同时需考虑s1如果小于0，则无法找零。当收到20元时，可分两种情况，找零5元和10元，或者找零3个5元。
      
      
