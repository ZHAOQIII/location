## 问题分析： 
Employee 表包含所有员工，他们的经理也属于员工。每个员工都有一个 Id，此外还有一列对应员工的经理的 Id。

给定 Employee 表，编写一个 SQL 查询，该查询可以获取收入超过他们经理的员工的姓名。在上面的表格中，Joe 是唯一一个收入超过他的经理的员工。


## 代码实现
```c
select e.Name as Employee  
from Employee e, Employee e1   
where e.ManagerId = e1.Id and e.Salary > e1.Salary ; 
```
## 总结：
声明Employee表的两个别名e和e1，通过as操作将结果字段名设置为Employee，然后select e的ManagerId字段与e1的Id字段相等，且e1的Salary大于e2的Salary。