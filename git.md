# git

## git是什么

Git是目前世界上最先进的分布式版本控制系统（没有之一）。本质上就是一款软件。

Git有什么特点？简单来说就是：高端大气上档次！

## 版本控制系统

管理源代码，主要有下面这些功能、

控制软件的版本

版本备份

代码合并

追溯问题责任人

分支管理

## 分布式

每个节点都是一个独立的服务器，可以独立服务，不需要依赖别人，大家之间也可以互相协作。



![](\mdimg\12.png)

## 集群式

集中式就是所有人都是客户端，要想备下载代码，都需要找服务器，一旦服务器挂了，集体放假。

![](mdimg\11.png)

### git命令

### 获取git的版本

```
git --version
```



#### 创建版本库

```
git init			不要用中文文件夹
```

#### 配置身份信息

```
git config --global user.email '110@sp.com'
git config --global user.name '老王'
```

#### 添加到版本库

添加到暂存区

```
git add 文件
git add .		添加所有文件到暂存区
```

查看仓库状态

```
git status
```

添加i到版本库

```
git commit -m '日志信息随便写'
```

#### 查看版本

```
git log
```

#### 回退版本

```
git reset --hard 版本号(没必要写全，写前几位就可以了)

如果从10版本回退到了7版本，要想重新跳回9版本
git reflog		查看历史版本号,再用上面的命令进行回退
```

#### 撤销修改

```
仅撤销工作区，尚未提交到暂存区的内容
git checkout -- a.txt

如何撤销暂存区的修改
git reset HEAD a.txt
```

#### 查看配置

```
git config -l
```

#### 忽略文件

再实际做项目的时候，我们往往会忽略很多文件或者文件夹，不向仓库里面提交，所以要配置忽略文件

```
配置忽略文件  
.gitignore

文件内容
target          //忽略这个target目录
angular.json    //忽略这个angular.json文件
log/*           //忽略log下的所有文件
css/*.css       //忽略css目录下的.css文件
```

## 远程仓库

最受欢迎是github，如果只是自己个人玩玩儿而已，也可以使用国内的码云.

github.com

gitee.com

### 创建远程仓库

注册，创建仓库

### 配置远程仓库



### 将本地代码同步到远程仓库

添加到本地版本库

配置远程仓库的地址

```
git remote add origin https://github.com/mmsqc/fff.git
git push  origin master
```

### 将远程仓库代码拉取到本地

```
拉取任何人的代码，但是本地仓库与远程仓库并没有建立联系
git clone url
```

### 展示github上面的项目

 http://htmlpreview.github.io/? 

## 分支管理

![](C:\Users\root\Documents\共享目录\代码\md\mdimg\13.png)

```
创建分支
git branch mingzi;

查看分支
git branch;

选择分支
git switch mingzi;

合并分支
git merge mingzi;
```