## 问题分析： 
给定一个整数数列，找出其中和为特定值的那两个数。
你可以假设每个输入都只会有一种答案，同样的元素不能被重用。


## 代码实现
```c
int* twoSum(int* nums, int numsSize, int target) {
			     int *p=(int*)malloc(2*sizeof(int));
			       for(int i=0;i<numsSize-1;i++){
			         for(int j=i+1;j<numsSize;j++){
			            if(nums[i]+nums[j]==target){
			                *p=i;
			                *(p+1)=j;
			            }
			             }
			    }
			    return p;
}
```
## 总结：

找出其中和为特定值的那两个数，输出位置信息。