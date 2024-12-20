# Git浅学习以及感想（后期可进一步完善）

> 张若晨

## 学习背景

+ 掌握Markdown语法、已建立自己的Github的仓库

## 学习内容的目录

- [Git为何会诞生](###Git诞生目的)
- [Git安装](###Git安装)
- [Git仓库创建以及文件添加](###仓库创建)
- [远程仓库](###远程仓库)
- [学习感想](###感想)

## 学习内容

### Git诞生目的

> + 诞生于减少不必要麻烦：
>     相互传递文档的时候需要仔细阅读并且寻找被修改的部分这一过程非常的繁琐且浪费时间，于是引起了人们的思考和改革，Git便应运而生了，它可以记录每次文件的改动以及改动的日期用户等，并且采用分布式版本控制系统，提高了文件保存的安全性和工作效率。

### Git安装

> + 遇到的问题：
>
>   直接使用官方网站安装pretty龟速，所以我选择去开源软件镜像站找到Git的下载链接进行安装:raising_hand:

### 仓库创建

> + 创建版本库：
>
> ```
> 使用命令mkdir 版本库名称（例如：mkdir learngit） //创建空版本库
> 使用命令cd 版本库名称（例如：cd learngit）//进入版本库
> 使用命令pwd //显示版本库所在位置
> ```

> + 初始化一个Git仓库：
>
> ```
> git init命令 //初始化版本库，使得该版本库能够被Git管理
> ls -ah命令 //可以查看空版本库下的.git目录
> ```

> + 添加文件到Git仓库，分两步:（==注意==：文件一定要先放在版本库目录名下）     
>
>     使用命令git add <file> //可反复多次使用，添加多个文件
>     使用命令git commit -m <message> //完成

### 远程仓库

> #### 准备工作
>
> 创建SSH KEY
>
> ==问题==：始终无法在用户目录下找到.ssh
>
> ==尝试解决==：
>
> - 思考—>用户名中文导致错误？—>将本机账户用户名改成英文—>无效
> - CSDN搜索—>直接在Git GUI中选择操作创建SSH 即可
>
> #### 添加远程库
>
> + 把本地库内容推送至远程库
>
> ```
> 在Github上面建立一个仓库
> git remote add origin git@git.com:deligentsheep/Tasks.git //添加Github上面我自个的远程库
> git push (-u) origin master //把本地库内容推送到远程库 ,如果远程库是空的话要加上括号里面的内容
> ```
>
> ==问题==：报错Could not read from remote repository
>
> + SSH警告
> + 删除远程库
>
> ```
> 先使用命令 git remote -v //查看远程库信息
> 使用命令git remote rm 远程库名字，这里是origin //根据名字删除远程库
> ```

> #### 从远程库克隆
>
> 要克隆一个仓库，首先必须知道仓库的地址，然后使用`git clone`命令克隆

### 感想

> - 感想：
>   - ”懒“人创造世界，但是前提是能解决问题的“懒”人
>   - 遇到网络龟速情况，可以考虑一下使用点小手段 
>   - 没有额外消息就是最好的消息:crying_cat_face:
>   - 真庆幸人有耐心这个品性，不然我的电脑可能已经四分五裂了…



