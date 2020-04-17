# 数据库  
### 概念(0227 第一周 第一次上课)
- 存放数据的仓库
- 增删查改  

### 信息与数据 (两个概念) 
- 信息:信息（Information）就是对各种事物的存在方式、运动状态和相互联系特征的一种表达和陈述，是自然界、人类社会和人类思维活动普遍存在的一切物质和事物的属性，它存在于人们的周围。  
- 数据:数据（Data）是用来记录信息的可识别的符号，是信息的具体表现形式。[数字/文字图/视频]  

### 数据处理
- 数据处理是指将数据转换成信息的过程，也称信息处理
- 数据处理的内容主要包括数据的收集、组织、整理、存储、加工、维护、查询和传播等一系列活动。
- 数据处理的目的是从大量的数据中，根据数据自身的规律和它们之间固有的联系，通过分析、归纳、推理等科学手段，提取出有效的信息资源。

## 数据描述
- 现实世界
- 信息世界

|实体（Entity）|客观存在并且可以相互区别的事物称为实体。实体可以是具体的事物，也可以是抽象的事件。| 一对一/一对多/多对多|
--|--|--|
|属性（Attribute）|描述实体的特性。一个实体可以用若干个属性来描述。|
|码（Key）|**唯一**标识实体的属性或属性的组合。|
|域（Domain）|属性的取值范围称为该属性的域。| 

- 数据世界

![现实世界中客观对象的抽象过程](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/1.png "现实世界中客观对象的抽象过程")  


----------

### （一）数据模型的分类(0227 第一周 第二次上课)

- 对现实世界的两层抽象: 概念模型(第一层)/数据模型(第二层)

## 概念模型  
- E-R模型(实体-关系模型)
- 矩形框表示实体
- 椭圆形表示实体属性
- 菱形表示实体的属性  


![教师授课E-R图](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/2.png "教师授课E-R图")

## 数据模型

### 层次模型：
  **用“树”结构来表示数据之间的关系**
### 网状模型：
   **用“图”结构来表示数据之间的关系**
### 关系模型


- 关系模型：用“表”结构（或称关系）来表示数据之间的关系
- 元组: 表中每行代表一个元组
- 属性:每列是一个属性
- 候选码:关系中某一属性或属性组的值能够唯标识一个元组， 把该属性或者属性组称为候选码
- 主码:选候选码中的一一个作为主码
- 关系模式:用来描述关系的表达式。学生(学号，姓名，性别，专业号，年龄)教师(教师号，姓名，性别，职称)
-  完整性:实体完整性:若属性A是表B的主属性，则属性A不能取空值。NULL
-  参照完整性:每一个主码用<span style="border-bottom:2px dashed yellow;">下划线</span>表示
-  外码:

![选择 投影](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/3.png "选择投影")
## 数据库相关概念
- 数据库:(Data Base，DB）存放数据的仓库,相关关联的集合.
- 数据库管理系统（Data Base Management System，DBMS）:用来操纵和管理数据库的大型软件



***
### 第二周第一次上课(0305)
### 数据库设计的六个阶段 ---学生选课系统

- 需求分析:了解客户需求,包括现阶段和潜在的需求
- 概念设计:在需求分析的基础上进行整理/归纳总结/形成E-R模型(实体/属性/联系)
- 罗技设计:把E-R模型转换为关系模型(表)
- 物理设计:进行存储结构和存取方法的选择。
- 数据库实施:前四个步骤依次迭代，发现问题解决问题，直到满足客户需求为止。
- 数据库运行和维护阶段:数据库投入使用之后，不断进一步调整的过程
### E-R模型
三个重要信息:
- 实体(矩形,框内写实体名字)
- 属性(椭圆,框内内写属性名字)
- 联系(菱形,内写名联系名)
设计步骤:设计局部E-R模型;合成全局E-R模型  
1:多对多M:P:N:Q.主码


### 逻辑设计阶段
- 转换规则:如果实体间关系是1-1,任何一个关系模式中加入另一个关系的主码和类型.  
![一对多](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/41.png "一对多")
方案1：“负责”与“职工”两关系模式合并。
职工（职工号，姓名，年龄，产品号）
产品（产品号，产品名，价格）


- 如果实体间关系是1:n :在M端中加入1端实体的关系模式和联系类型的属性.
仓库（仓库号，地点，面积）
产品（产品号，产品名，价格，仓库号，数量）

- 如果实体之间是m:n的关系,则实体之间的联系也要转换成一个关系模式，包含两端实体的主码和联系类型的属性。每个实体和自己的属性组成一一个关系模式。
![多对多](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/5.png "多对多")
***
### 第二周第二次上课(0306)
### 了解SQL语言: 结构化查询语言
#### 分类
- 数据定义语言(DDL,Data Definition Language) :
  负责数据库本身以及数据库中本身各种对象***的创建(Create语句)/修改(Alter语句)和删除(Drop语句)操作.而不是数据本身.***
- 数据操纵语言(DML,Data Manipulatino Language)
主要负责表中数据的更新,包括***增加(Insert语句)/删除(Delete语句)/修改(Update语句)/查询(Select)***.
- 数据控制语言(DCL,Data Control Language)
主要负责对数据库的安全管理/事物管理/指针控制等操作.

#### 了解MySQL数据库
- 启动与停止MySQL服务的两种方法
1.任务管理器 服务 找到MySQL 服务启动
2.CMD窗口net start mysql57(版本号)  关闭 stop
```
net start mysql57 #启动
net stop mysql57 #关闭
```
- 登录MySQL服务器的三中方式
1.Cmd窗口中  Mysql -h 主机名 -u 用户名 -p密码
Localhost/127.0.0.1 (主机名若登录为自己电脑 可省略)
```
mysql -h 主机名 -u 用户名 -p密码 #Localhost/127.0.0.1 (主机名若登录为自己电脑 可省略)
```
exit/quit退出
2.客户端直接登录
3.在MySQL管理软件中登录
- 给root用户修改密码的两种方式
```
Mysqladmin -u root -p旧密码 password 新密码 #在CMD中
set password for 'root'@'localhost'=password('123'); #在MySQL中
命令后面 必须有 ; 
```
- **创建数据库**:

| information_schema |
|--|
| mysql              |
| performance_schema |
| sys                |
四个基本数据库 
```
Create database 新建数据库名字;
create database if not exists 新建数据名字; #如果不存在新建
```
- 常见字符集 gb2312 gbk utf8
```
Create database 新建数据库名字 default character set utf8;# 新建一个数据库设置字符集为utf8
```
- 打开数据库
```
use 数据库名字; #Navicat中双击需要数据库名字
```
- 删除数据库
```
drop database 数据库名字; #一次只能删除一个
```


## 第三周第一次上课(0312)

### 表的命名
- 简单明了
- 最长不超过64个字符
- 简单明了 字母/数字(不做开头)/下划线 


- 1数值类型
 - 整数类型: tinyint smallint mediumint int bigint
 - 浮点类型: float double decimal
![数值类型](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/6.png "数值")
- 2.字符串类型
Char varchar text blob
![字符串](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/7.png "字符串")
- 3时间类型
 Date year time
![时间](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/8.png "时间类型")
### create table 创建表
#### 语法格式  

```
create table 表名

( 字段1 数据类型1 [列级完整性约束条件],
  字段2 数据类型2 [列级完整性约束条件],
  字段3 数据类型3 [列级完整性约束条件],
      .......
  字段n 数据类型n [列级完整性约束条件]
):
```

- 列级约束条件
 - 主键 :Primary key
 - 非空 :Not Null
 - 默认值 default

## 第三周第二次上课(0313)
### 表级约束性条件:
- 设置主键(表中至少有两个字段是主键时需要设置)
```
(
Constraint 约束名 primary key(字段1,字段2,...)  #放在语句后
);
```
 - eg:
```
create table floor
(sfloor char(6) not null,
sroomno char(6) not null,
stotal char(10),
maxn char(2) NOT NULL DEFAULT '六层',
constraint A primary key(sfloor,sroomno)
);
```

- 外键(一定是另外一个表中的主键)
- 外键约束如何设置:
```
Constraint约束名Foreign Key(外键字段名)References 被参考表名(外键字段名/也就是被参考表的主键)
```
 - eg
```
create table sc
(cno char(6) NOT NULL,
sno int(6) NOT NULL,
degree FLOAT(4,2),
cterm CHAR(6)NOT NULL,
CONSTRAINT asd PRIMARY KEY(cno,sno,cterm),
CONSTRAINT c8 FOREIGN KEY (cno,cterm) REFERENCES course(cno,cterm),
CONSTRAINT c6 FOREIGN KEY (sno) REFERENCES student(sno)
);
```
 - eg
```
create table craching
(cno char(6) NOT NULL,
tno char(12) NOT NULL,
cterm CHAR(6)NOT NULL,
CONSTRAINT w1 PRIMARY KEY(cno,tno,cterm),
CONSTRAINT w3 FOREIGN KEY (cno,cterm) REFERENCES course(cno,cterm),
CONSTRAINT w2 FOREIGN KEY (tno) REFERENCES teacher(tno)
);
``` 
## 第四周第一次上课(0319)
### 插入单条记录
#### 语句格式
```
insert into 表名 [(列名清单)省略默认添加所有字段的值] values(值1,值2,值3....)
# 如果列约束 nut null 必须添加
### 例子
insert into student(sno,sname,ssex,sbirthday) values(201901,'礼赞','男',20010329);
```
### 插入多条记录
```
insert into 表名 [(列名清单)省略默认添加所有字段的值] values(值1,值2,值3....),(值1,值2,值3....),(值1,值2,值3....)....
```
### 查看表的结构
```
describe 表名
# 可以简写 desc 表名
```

### 查看表的详细结构
```
show create table 表名
```
### 查看当前数据库中有哪些表
```
show tables
```
## 修改表结构
### alter table 表名 add
```
alter table 表名 add 新字段名 数据类型 列级约束性描述

alter table student add inyear year default '2019';
## 向已存在字段后添加
alter table 表名 新字段名 数据类型 列级约束性描述 after 已存在的字段名
# first 第一列

```

## 第4周第二次上课(0320)
### alter table 表名 change修改字段名
```
alter table 表名 change <旧字段名><新字段名><数据类型>;
# 对指定表中字段名进行改名.若不需要修改字段名,可将新数据类型设置成与原来一样,数据类型不能为空.

```
### alter table 表名 modify 修改数据类型 列级
```
alter table 表名 Modify <字段名><数据类型>[<列级性属性描述>];
alter table student modify ssex varchar(20) default '女' not null;
# 对表中的 数据类型修改 或者完整约束性条件进行修改.可将新数据类型设置成与原来一样,数据类型不能为空. 如果约束性条件不做修改,则要把原来的写上.
```
### alter table 表名 drop 删除字段名  删除表级约束

```
alter table 表名 drop<字段名><表级完整性约束名>; 对指定表中不需要的字段或者表级完整性约束进行删除.

alter table student drop inyear;
alter table student drop foreign key 键名;

```
### alter table 表名 rename 指定表重命名
```
Alter table表名Rename <新表名>: 对指定表的表名进行重命名。
```
### alter table 表名 engine
```
Alter table表名Engine=<更改后的存储引擎名>:对指定表的存储引擎进行修改。
```
## 复制表
```
CREATE TABLE新表名 SELECT * FROM旧表名;

```
## 删除表
```
drop table 表名
```
## 添加外键约束 
```
alter table 表名 add Constraint约束名Foreign Key(外键字段名)References 被参考表名(外键字段名/也就是被参考表的主键)
```  

## 第五周第一次上课(0326)
### 三范式
- ***三范式:目前关系数据库有六种范式:第一范式(1NF)、 第二范式(2NF)、第三范式(3NF)、巴斯-科德范式(BCNF)、 第四范式(4NF)和第五范式(5NF，又称完美范式)。***满足最低要求的范式是第一范式(1NF)。在第一范式的基础上进一步满足更多规范要求的称为第二范式(2NF),其余范式以此类推。-般说来，**数据库只需满足第三范式**
 - 第一范式(1NF): 是指设计的表中每一列都是不可拆分的原子项.
 - 第二范式(2NF): 在第一范式的基础上非主键字段完全依赖于主键字段.  若不符合二范式则会有以下问题:
   - 数据冗余: 
   同一门课程由n个学生选修，“学分”就重复n-1次:同一个学生选修了m门课程，姓名和年龄就重复了m-1次。
   - 更新异常:
   若调整了某门课程的学分，数据表中所有行的学分"值都委更新，否则会出现同一门课程学分不同的情况。
   - 插入异常:
   假设要开设一门新的课程，暂时还没有人选修。这样，由于还没有"学号"关键字，课程名称和学分也无法记录入数据库。
   - 删除异常:
   假设一- 批学生已经完成课程的选修，这些选修记录就应该从数据库表中删除。但是，与此同时，课程名称和学分信息也被删除了。很显然，这也会导致插入异常。
![拆分后](https://gitee.com/yunaks/MySQL-ClassNote/raw/ff3e0afce3616e244526b61ad1c42e91fdcee0dd/image/9.png "拆分后解决")


授课信息表（课程号，教师号，课程名称，教师姓名，所在教室，授课时间）  
  

课程表(课程号 课程名称 )
教师表(教师号 教师姓名 )
授课表(课程号 教师号 所在教室，授课时间)
  - 第三范式:
   - 表中非主键字段只能依赖于主键字段,不能依赖于其他非主键字段

## 第五周第二次上课(0327)
### select查询语句
  

```
SELECT 子句1
FROM 子句2
[WHERE 表达式1]
[GROUP BY 子句3
[HAVING 表达式2]]
[ORDER BY 子句4]
[UNION 运算符]
[LIMIT [M,]N]
[INTO OUTFILE 输出文件名];
```  

- 表单无条件查询
```
  语法: 查询所有字段 select * from 表名  

  查询部分字段 select 字段名1,字段名2 from 表名
  
  select sname,sno, sdept from student 
```
- 
- 重 distinct  
```
select distinct 字段名1,字段名2 from 表名
```
- 返回结果前N行 limit [M],N m表示从第m行开始 n是几行
```
select * from student limit 0,2
```
- 日期 
```
select sname,year('2当前日期')-year(日期列) from student
select sname,year('2020-03-27')-year(sbirthday) from student
select sname,year(CURDATE())-year(sbirthday) from student
```
- 设置显示的列名 as
```
select 字段名1 as '指定列名'
select sname as '姓名',year(sbirthday) as '出生年份',sdept as '所在系' from student  
```  

# 条件查询

|查询条件	   |运 算 符|
--|--|--
|比较运算符|	=,<,>,<=,>=,<    >,!=,!<,!>|
|范围运算符	|BETWEEN AND,NOT BETWEEN AND|
|列表运算符	|IN,NOT IN|
|字符匹配符	|LIKE,NOT LIKE|
|空值	|IS NULL,IS NOT NULL|
|逻辑运算符	|AND,OR,NOT|  
### where条件查询
```
SELECT [ALL|DISTINCT] <字段名1> [AS<显示列名>] [,<字段> [AS<显示列名>][,…]]
FROM <表名|视图名> [limit[M],N]
WHERE <条件表达式>;
```  
#### 比较运算符 
```
select 字段 from 表名 where ssex='男'
```
#### 逻辑运算符 and or not
```
where 逻辑表达式1 逻辑运算符 (and/or) 逻辑表达式2 
SELECT * from student where ssex='男' and sdept='计算机工程系'; 
where not  逻辑表达式
```
# 范围运算符 between ... and ... 
```
where 表达式 [not] between 初始值 and 终止值
不允许初始值大于终止值
select sno,degree from sc where degree between 80 and 90
```

## 第六周第一次上课(0402)
### 字符运算符
- 格式 
```
where 字段名 [not] like '字符串'
```  
- 
-  % :任意多个字符 _:任意一个字符

### 列表运算符 
```
wehere 表达式 [not] in 值列表
```
### 涉及空值的查询 
```
where 字段 is [not]null
```
### 聚集函数

|  聚集函数| 具体用法    | 具体含义 |
--|--|--|
|count|count([distinct/all]*)|统计元组个数|
|count|count([distinct/all]<列名>)|统计一列中值的个数
|SUM|SUM[DISTINCTALL]<列名|计算列值的总和(此列必须为数值型|
|AVG|  AVG([DISTINCT/ALL] <列名>) | 计算一列值的平均值（此列必须为数值型）  |
|MAX| MAX([DISTINCT/ALL] <列名>)  | 求一列值中的最大值  |
|MIN| MIN([DISTINCT/ALL] <列名>)| 求一列值中的最小值  |
```
# 1、查询学生总数。
select count(sno) from student
# 2、查询选修了课程的学生人数。
select count(distinct sno) from sc
# 3.计算002号课程的学生平均成绩。
select avg(degree) from sc where cno='c02'
# 4、查询选修了002号课程的学生最高分和最低分，列名分别为最高分和最低分。
select max(degree) as '最高分', min(degree) as '最低分' from sc where cno='c02'
# 5、查询学号为“2005010101” 的学生的总成绩及平均成绩。
select avg(degree) from sc where sno=2005010101
# 6、查询有考试成绩的学生人数。
select count(DISTINCT sno) from WHERE degree is not null
```
### 分组筛选数据 grop by
```
select 字段名,筛选范围 from 表名 [GROUP BY 列名清单 [HAVING 条件表达式]]
select ssex,count(*) from student group by ssex
```
## 第六周第二次上课(0403)
### 排序order by
```
[ORDER BY <列名1> [ASC|DESC][,<列名2> [ASC|DESC]][,…]]
```
- **如果只有一个列名，则按该列名值进行排序
如果有多个列名，先按第一个列名值排序，第一个列名值相同的，再按第二个列名值进行排序，以此类推。
默认情况使用升序ASC进行排序，如果要求降序排序，自行指定，采用Desc 字段。**
```
# 查询全体学生情况，查询结果按所在系升序排列，同一系中的学生按出生日期降序排列。
select * from student order by convert(sdept using gbk) DESC
```  

## 多表链接查询
### 交叉力链接
```
SELECT [ALL|DISTINCT] [别名.]<选项1> [AS<显示列名>] [,[别名.]<选项2> [AS<显示列名>][,…]]
FROM <表名1>[别名1] ,<表名2>[别名2]；
eg:select course.*,sc.* from course,sc
```
### 内连接
```
SELECT [ALL|DISTINCT] [别名.]<选项1>[AS<显示列名>] [,[别名.]<选项2>[AS<显示列名>][,…]]
FROM <表名1> [别名1],<表名2> [别名2][,…] 
WHERE <连接条件表达式> [AND <条件表达式>];
select 表名1.*,表名2.* from 表名1,表名2 where <链接表达式> [and <链接表达式>]
eg:select student.*,sc.* from student,sc where student.sno=sc.sno
```
```
SELECT [ALL|DISTINCT] [别名.]<选项1>[AS<显示列名>] [,[别名.]<选项2>[AS<显示列名>][,…]]
FROM <表名1> [别名1] INNER JOIN <表名2> [别名2] ON <连接条件表达式>
[WHERE <条件表达式>];
select 表名1.*,表名2.* from 表名1 inner join 表名2 on 链接表达式
eg:select student.*,sc.* from student inner join sc on student.sno=sc.sno

```
### 自连接
多表链接不止可以在不同的之间链接,也可以在同一张表内进行
```
select 别名1.字段1,别名1,字段2 from 表名 别名1,表名 别名2 where 条件表达式
# 同时选修了c01和c02课程学生学号
select A.sno from sc A,sc B where A.cno='c01' and b.cno='c02' and A.sno=B.sno
# 查询和刘晨在一个系的学生的学号、姓名和系别
select A.sname,A.sno,A.sdept from student A,student B where A.sdept=B.sdept and B.sname='刘晨'and A.sname!='刘晨'
```
## 第Ⅶ周第一次上课(0409)
### 外连接
1、外连接 在自然连接中，只有在两个表中匹配的行才能在结果集中出现。而在外连接中可以只限制一个表，而对另外一个表不加限制(所有的行都出现在结果集中)。 

```
语法格式:select表名1.*,表名2.* from 表名1 left| right|full join表名2 on 连接表达式
``` 
例:用左外连接查询每个学生选修课程的情况
```
select student.*,sc.* from student left join sc on student.sno=sc.sno
```
由于mysql不支持全连接采用并链接union代替 full
```
select 表名1.*,表名2.* from 表名1 left join 表名2 on链接表达式 union select 表名1.*,表名2.* from 表名1 right join 表名2 on链接表达式
eg:
select student.*,sc.* 
from student left join sc on student.sno=sc.sno union 
select student.*,sc.* 
from student right join sc on student.sno=sc.sno
```
### 嵌套查询
- 把一个select...from...where...语句称为一个查询块
.将一个查询块嵌套在另一个where子句中,称谓嵌套查询.过程为首先执行子查询，子查询得到的结果集不被显示出来，而是传给外部查询，作为外部查询的条件使用，然后执行外部查询，并显示查询结果。子查询可以多层嵌套。
- 语法格式
```
select 字段名 from 表名 where 字段名=/in(select 字段名 from 表名 where)
eg:查询选修了c02的学生姓名
select sname from student where sno in(select sno from sc where cno='c02')
```


## 第Ⅶ周第二次上课(0410)
### any和all操作实现查询
- any是查询结果中的某个值 >< >= <= = !=
- all是查询结果中的所有值
### 相关子查询
- 在相关子查询,子查询的执行依赖于父查询
select sname from student where EXISTS
(select * from sc where cno='c01' and sno=student.sno)
执行过程:首先取出李勇的学号，2005010101,然后将该学号传入子
查询，子查询中有与之.匹配的内容，将李勇姓名输出
再取出刘晨的学号，2005020201,把该学号传入子查询中，没有匹配
项，父查询不输出内容
取出张立的学号，2005020202,把该学号传入子查询中，没有匹配项，
父查询不输出内容
取出王敏的学号，2005030301,把该学号传入子查询中，没有匹配项，
父查询不输出内容
### 集合查询
MySQL语言只支持UNION（并操作）运算
相当于逻辑运算的OR功能



## 第八周第一次上课(0410)


**总结:如果要查询并显示的字段在一个表中，则可以使用多表连接和嵌套查询。如果这些字段不在-个表中，那么只能使用多表连接查询。**
### 数据更新
### 插入多条记录
```
insert into 表名 [(列名清单)省略默认添加所有字段的值] values(值1,值2,值3....),(值1,值2,值3....),(值1,值2,值3....)....
```
### 将查询结果保存到另一个表
```
insert into student1(已经存在的) select * from student where ssex='女'
```
### 数据记录的修改updated 表名
```
updated 表名 set 字段名=表达式[where <条件表达式>]
# 若有where表达式,则修改满足where条件表达式的行,如果省略,则对表中所有行进行修改
```
### 对表中的记录进行删除
```
delete from 表名 [where 条件表达式]
若有where子句,删除表中满足条件的行
若没有where子句,删除表中所有数据保留该表结构
``` 