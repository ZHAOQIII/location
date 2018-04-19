## 问题分析： 
报数序列是指一个整数序列，按照其中的整数的顺序进行报数，得到下一个数。。


## 代码实现
```c
class Solution {
public:
	string countAndSay(int n) {
		if (n <= 0) return "";
		string res = "1";
		while (--n) {
			string current = "";
			for (int i = 0; i < res.size(); ++i) {
				int count = 1;
				while (i + 1 < res.size()&&res[i]==res[i+1]){
					++count;
					++i;
}
				current += to_string(count) + res[i];
			}
			res = current;
		}
		return res;

	}
};
```
## 总结：
先对n进行判断，循环当前数，在循环的同时对相同的数进行计数，当碰到两个数不同时进行字符串拼接（数目＋当前数），计数置为1。