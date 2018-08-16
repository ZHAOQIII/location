## 问题分析： 
我们要把给定的字符串 S 从左到右写到每一行上，每一行的最大宽度为100个单位，如果我们在写某个字母的时候会使这行超过了100 个单位，那么我们应该把这个字母写到下一行。我们给定了一个数组 widths ，这个数组 widths[0] 代表 'a' 需要的单位， widths[1] 代表 'b' 需要的单位，...， widths[25] 代表 'z' 需要的单位。

现在回答两个问题：至少多少行能放下S，以及最后一行使用的宽度是多少个单位？将你的答案作为长度为2的整数列表返回。
## 代码实现
```c
class Solution {
public:
    vector<int> numberOfLines(vector<int>& widths, string S) {
         int s1=S.size(),sum=0,row=0;
    for(int i=0;i<s1;i++)
    {
        sum+=widths[S[i]-'a'];
        if(sum>100)
        {
            sum=widths[S[i]-'a'];
            row++;
        }
    }
    return {row+1,sum};  
    }
};
```
## 总结：
以widths[0] 代表 'a'为基准，依次遍历字符串S，累计字符串的长度，当大于100时，row++，并将下一行的字符串的初始长度置为上一行最后一个字符的长度。
      
      
      