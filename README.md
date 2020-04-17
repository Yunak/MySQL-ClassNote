## 四月十七 
### 查询知识点总结 
#### 单表无条件查修
 - 查询所有字段信息：select *from 表名
 - 查询部分字段信息：select 字段名1，字段名2 from 表名
 - 查询结果中去重：distinct
  select distinct sno from sc
 - 返回查询结果中某几行：limit M，N 表示从第M行开始（默认0）,返回结果中的 N行
 - 设置显示的列名:as 重命名

### where子句条件查询
 - 语法: select ...from 表名 where 表达式
 - 比较运算符 >< = >= !=
 - 逻辑运算符 and or not
 - 范围运算符 between 初始值 and 终止值
 - 字符运算符: like
   通配符%:任意多个字符 _:任意一个字符  

#### 列表运算符 in not in
例:
```
查询 信息工程系/软件工程系/计算机工程系 学生的姓名性别
select sname,ssex from student where sdept in('信息工程系','软件工程系','计算机工程系')
```
#### 空值的查询 is null /is not null
```
例:查询成绩非空的学生的学号、课程号和对应成绩
Select sno,cno,degree from sc where degree is not null
```
### 使用凝聚函数统计数据
 - count(*) 统计元组个数
 - count(字段名)统计该列中值的个数
 - Count (字段名)统计该列中值的个数
 - Sum (列名)计算-一列值的总和
 - Avg (列名)计算一列值的平均值
 - Max (列名)求一列中的最大值
 - Min (列名)求一列中的最小值
### 分组筛选函数 group by
 - 语法格式 select ...from 表名 group by 列名清单 [having 条件表达式] 

```
统计各系女生人数
select sdept,count(*) from student where ssex='女' group by sdept
select sdept,count(*) from student group by sdept,ssex having ssex='女'
```
### 对查询结果排序 
 - 语法格式: order by 字段名 asc/desc 
默认asc(升序)  需要降序时间 desc

### 多表链接
#### 交叉链接
 - 交叉连接:对两个表做笛卡尔积，得到结果的行数为两个表行数的乘积，得到结果的列数为两个表列数的和。

 
#### 内链接
 - 语法:

 ```
select字段名1，字段名2...from表名1,表名2 where连接条件表达式
Select字段名1,字段名--.from表名1 inner join 表名2 on 连接条件表达式
```

#### 自连接
 - 将一个表不同行连接起来　　  
 

### 外连接分为左外连接、右外连接、全外连接
 - 在外连接中可以保留不匹配的行的信息

### 嵌套查询
#### 嵌套子查询
- 把一个Select- From- where子句语句称为一个查询块，将一个查询块嵌套在另一个查询块的where子句中的形式称为嵌套查询或子查询
例:查询选修了CO2课程学生的姓名

```
Select sname from student where sno in (Select sno from sc where ono='d02')
```
- 子查询的执行是独立的,不依赖父查询.子查询结果不显示,但是吧查询结果传递给父查询,作为父查询的条件

#### 相关子查询
- 相关子查询中,子查询执行依赖父查询

