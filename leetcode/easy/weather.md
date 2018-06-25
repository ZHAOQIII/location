## 问题分析： 
给定一个 Weather 表，编写一个 SQL 查询，来查找与之前（昨天的）日期相比温度更高的所有日期的 Id。


## 代码实现
```c
select w1.id from Weather w1,
Weather w2
where w1.Temperature>w2.Temperature and SUBDATE(w1.RecordDate, 1) = w2.RecordDate;
```
## 总结：
找出温度大于前一天的id，并形成新的表。