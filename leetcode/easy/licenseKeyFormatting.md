## 问题分析： 
给定一个密钥字符串S，只包含字母，数字以及 '-'（破折号）。N 个 '-' 将字符串分成了 N+1 组。给定一个数字 K，重新格式化字符串，除了第一个分组以外，每个分组要包含 K 个字符，第一个分组至少要包含 1 个字符。两个分组之间用 '-'（破折号）隔开，并且将所有的小写字母转换为大写字母。

给定非空字符串 S 和数字 K，按照上面描述的规则进行格式化。
## 代码实现
```c
class Solution {
public:
    string licenseKeyFormatting(string S, int K) {
        string res;
        int i=S.size()-1,count=0;
        while(i>=0)
        {
            if(S[i]!='-')
            {
                count++;
                if(count<=K)
                {
                    res+=char(toupper(S[i]));
                    i--;
                }
                else
                {
                    res+='-';
                    count=0;
                }
            }
            else
                i--;
        }
        reverse(res.begin(),res.end());
        return res;
    }
};
```
## 总结：
先每隔K个字符插入‘-’，形成字符串res，然后字符串反转，即为所求字符串。