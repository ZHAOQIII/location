## 问题分析： 
你现在是棒球比赛记录员。
给定一个字符串列表，每个字符串可以是以下四种类型之一：
1.整数（一轮的得分）：直接表示您在本轮中获得的积分数。
2. "+"（一轮的得分）：表示本轮获得的得分是前两轮有效 回合得分的总和。
3. "D"（一轮的得分）：表示本轮获得的得分是前一轮有效 回合得分的两倍。
4. "C"（一个操作，这不是一个回合的分数）：表示您获得的最后一个有效 回合的分数是无效的，应该被移除。

每一轮的操作都是永久性的，可能会对前一轮和后一轮产生影响。
你需要返回你在所有回合中得分的总和。
## 代码实现
```c
class Solution {
public:
    int calPoints(vector<string>& ops) {
  if(ops.size()==0)return 0;
  vector<int>score;
  for(auto s:ops)
  {
    if(s == "C")score.pop_back();
    else  if(s == "D")score.push_back(score.back()*2);
    else  if(s == "+")score.push_back(score[score.size()-1]+score[score.size()-2]);
    else  
    {score.push_back(atoi(s.c_str()));
    }
  }
  int sum = 0;
  for(auto a:score)cout<<a<<" ",sum+=a;
  return sum;  
    }
};
```
## 总结
依次遍历字符串列表：
"+"（一轮的得分）：表示本轮获得的得分是前两轮有效回合得分的总和。
 "D"（一轮的得分）：表示本轮获得的得分是前一轮有效回合得分的两倍。
"C"（一个操作，这不是一个回合的分数）：移除当前值。
最后对数组进行依次累加。
      