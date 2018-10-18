# 实验一：分析SQL执行计划，执行SQL语句的优化指导
本次数据库包括了职工的基本信息和在公司的编号，工资等，涉及的语句比较简单，一方面要顾及查询语句不能太简单检测语句的效率，一方面要多行数据进行查询，本人认为老师的查询查询语句最佳，可以看出查询语句的优劣，如下是实验内容。
* 查询语句1
```sql
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
from hr.departments d，hr.employees e
where d.department_id = e.department_id
and d.department_name in ('IT'，'Sales')
GROUP BY department_name;
```
* 查询语句2
```sql
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
FROM hr.departments d，hr.employees e
WHERE d.department_id = e.department_id
GROUP BY department_name
HAVING d.department_name in ('IT'，'Sales');
```
## 查询结果
![Mou icon](https://github.com/supermanliuyang/Oracle/blob/master/result.png)
## sql语句1
![Mou icon](https://github.com/supermanliuyang/Oracle/blob/master/plan1.1.png)
![Mou icon](https://github.com/supermanliuyang/Oracle/blob/master/plan1.png)
## sql语句2
![Mou icon](https://github.com/supermanliuyang/Oracle/blob/master/plan2.1.png)
![Mou icon](https://github.com/supermanliuyang/Oracle/blob/master/plan2.png)
## 本人设计的语句（在老师的基础上改了查询的名字）
![Mou icon](https://github.com/supermanliuyang/Oracle/blob/master/plan3.png)
![Mou icon](https://github.com/supermanliuyang/Oracle/blob/master/plan3.1.png)
