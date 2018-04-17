## 问题分析： 
给定一个只包括 '('，')'，'{'，'}'，'['，']' 的字符串，判断字符串是否有效。

有效字符串需满足：

括号必须用相同类型的右括号闭合。

左括号必须以正确的顺序闭合。

字符串为空。


## 代码实现
```c
class Solution {
public:
    bool isValid(string s) {
        int num=s.length();
        if(num%2!=0)
            return false;
        for(int i=0;i<num/2;i++)
        {
            for(int j=0;j<s.length()-1;j++)
            {
                if((s[j]=='['&&s[j+1]==']')||(s[j]=='('&&s[j+1]==')')||(s[j]=='{'&&s[j+1]=='}'))
                {
                    if(s.length()==2)
                    {
                        return true;
                    }
                    else
                    {
                        s=s.substr(0,j)+s.substr(j+2);
                    }                    
                }
            }
        }
        return false;
    }
};
```
## 总结：
采用入栈的方式，后进先出的特征正好满足检测的需求。在检测的时候，每次检查一个字符，如果是左括号，就入栈，如果是右括号，并且右括号和当前栈顶符号是左右配对的，那么就弹出栈顶并且进行下一次检测，如果不满足上面两种情况，就说明检查到了一个非法字符，返回false。