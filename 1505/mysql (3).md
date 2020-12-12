# 数据库

## 什么是数据库

宏观上来说：存储数据的仓库

微观上来说：就是一堆数据

## 主要功能

数据存储

数据操作（学习)

数据安全

数据迁移

## 操作软件（数据库管理系统)

常见的数据库软件

​		oracle		甲骨文公司，大型的，性能好，价格贵，市场占有率高。

​       sqlserver	微软公司，中型数据库，收费

​	   mysql          甲骨文公司，中小型数据库，免费，市场占有率特高

## mysql数据库

## 介绍：

MySQL是一个**[关系型数据库管理系统](https://baike.baidu.com/item/关系型数据库管理系统/696511)****，**由瑞典MySQL AB 公司开发，属于 [Oracle](https://baike.baidu.com/item/Oracle) 旗下产品。MySQL 是最流行的[关系型数据库管理系统](https://baike.baidu.com/item/关系型数据库管理系统/696511)之一，在 WEB 应用方面，MySQL是最好的 [RDBMS](https://baike.baidu.com/item/RDBMS/1048260) (Relational Database Management System，关系数据库管理系统) 应用软件之一。

MySQL是一种关系型数据库管理系统，关系数据库将数据保存在不同的表中，而不是将所有数据放在一个大仓库内，这样就增加了速度并提高了灵活性。

MySQL所使用的 SQL 语言是用于访问[数据库](https://baike.baidu.com/item/数据库/103728)的最常用标准化语言。MySQL 软件采用了双授权政策，分为社区版和商业版，由于其体积小、速度快、总体拥有成本低，尤其是[开放源码](https://baike.baidu.com/item/开放源码/7176422)这一特点，一般中小型网站的开发都选择 MySQL 作为网站数据库。

## mysql数据库管理系统（dbms--database manager system)

一个mysql数据库里面可以包含很多的库(database)  --   每个库存放一个独立的系统数据

一个库里面的数据会分布到不同的表(table)里面去 -- 每个表存放的是一些有关联的数据

一个表里面有很多的列，比如学生表(编号,名字,地址,电话)

其实写列是有要求的。一个列有几大组成部分

   列名称           列类型                                           					   长度                    约束

​	编号            int(整型)/varchar(字符串) /double(小数)                   20                 唯一约束,空约束,主键约束，外键约束

如果是字符串类型，长度是必须要写的。不能省略。

如果是数字类型，长度可以省略，默认长度为11 



## 安装数据库

根装qq一样装

要想使用myslq，必须先启动mysql的服务。

## 服务管理

1.服务--》启动或者关闭

2.管理元命令行窗口-->启动(net start mysql)    -->关闭(net stop mysql)

## 连接数据库

```
mysql -h ip地址 -u 用户名 -p密码

注意：如果连接本机的mysql数据库，ip地址可以省略。
```

```
连接之后想要退出mysql数据库

exit
```

创建用户并授权

```
创建了一个用户叫做laowang,%表示任何人都可以登录,第二个老王表示密码
create user laowang@'%' identified by 'laowang';

授予所有的库的所有的表的苏颇有的权限给laowang.
gant all privileges on *.* to laowang@'%';

刷新权限
flush privileges;

localhost		表示本机     
127.0.0.1		表示本机
```

## 库操作

```
查看有哪些库			show--展示    database--数据库      change---改变
show databases;

查看当前是哪个库
select database();


选择仓库
use 库名;

创建库          --模式使用utf8编码(支持中文)
create database 库名 default charset utf8;

删除库
drop database 库名;
```



## 表操作

```
查看当前库有哪些表			table--表的意思
show tables;

创建表
create table emp(
	no int,
	name varchar(30),
	age int,
	addr varchar(255),
    tel varchar(11),
    salary	double
);

查看表结构
desc 表名;


修改表结构
    修改表名
    alter table test rename to test2;

    增加一个列
    alter table test add column age int;

    删除一个列
    alter table test drop column age ;

    修改列的类型或者约束
    alter table test modify name int; 
    
    修改列的类型或者约束以及列名
    alter table test change name name88 varchar(88);

    调整字段顺序 
    alter table test change name name varchar(88) after no;

删除表
drop table 表名;
```

### 条件(where)

等于(不等于)

​		select * from emp where name = "金毛"	-- 查询emp表所有名字等于金毛的数据

​		select * from emp where name != '金毛'    --  查询emp表所有名字不等于金毛的数据

​		select * from emp where name <> '金毛'    --  查询emp表所有名字不等于金毛的数据

大于(大于等于)

​		select * from emp where age > 30;	--	查询emp表所有年龄大于30的数据

​		select * from emp where age >= 30;	--	查询emp表所有年龄大于等于30的数据

小于(小于等于)

​		select * from emp where age < 30;	--	查询emp表所有年龄大于30的数据

​		select * from emp where age <= 30;	--	查询emp表所有年龄大于等于30的数据

模糊查询(like)

​		like '金' 		<===>           =   '金'

​		select * from emp where name like '%王%';		--  查询emp表所有名字包含王字的数据

​        select * from emp where name like '王%';			-- 查询emp表所有姓王的数据

​		select * from emp where name like '_王%';		 -- 查询emp中所有名字的第二个字是王字的数据

​		select * from emp where name like '___';			-- 查询emp表中所有名字是3个字的人的数据

and(既满足这个条件又要满足那个条件)              ----    

​		select * from emp where name like '__' and age < 80;	--	查询所有名字是两个字的，并且年龄小于80的人的数据

or（满足这个条件，或者满足那个条件)

​		 select * from emp where age < 80 or name88 like '%毛%';	--  查询所有年龄小于80，或者名字带毛字的人的数据

between ..  and  (在。。。之间)         not between and (不在。。。之间。。。)

​		select * from emp where age not between 30 and 80;

in(在。。。里面)				not  in(不在。。。里面)

​	select * from emp where name88 in ('小王','小明','金毛');		--   查询名字叫小王或者小明或者金毛的人的数据

is null(是空)			is not null （不是空)



### 数据查询

```
查询所有数据
select * from 表名;

查询指定列的数据
select name,age from emp;

可以给别名
select name 名字,age 年龄,addr 地址 from emp;

查询某列不重复的数据
select distinct sex from emp;
```
升序；
 select * from lsb order by xb;
 降序；
  select * from lsb order by xb desc；
  


### 数据更新

​	update emp set name = '老王',age=21,addr='隔壁' where id < 10;

### 数据删除

​	delete from emp where no = 1;

### 数据添加

```
插入所有数据
insert into 表名 values (第一列的值，第二列的值，第三列的值....),(第一列的值，第二列的值，第三列的值....);

部分列插入数据
insert into 表名(列名，列名，列名) values (值1，值2，值3), (值1，值2，值3);
```

每个表至少5条数据以上

创建班级表（班级编号，班级名称，辅导员)

创建学生表(学号，名字，年龄，性别，电话，住址，身份证,班级编号)

创建科目表(科目编号，科目名称)

创建老师表(编号，名字，性别，年龄)

老师科目表(老师编号   科目编号)





