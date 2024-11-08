## Git版本回滚以及冲突解决



### 版本回滚

> - 从当前版本回退
>
>   - 首先查看所有的状态，也就是所有的提交记录：git log –pretty=oneline
>
>   - 显示出来的记录中：HEAD表示当前版本，上一个版本就是HEAD\^,上上一个版本就是HEAD^^,但是数量较多的话这样就不是很方便，所以我们直接写成HEAD\~往前回去的版本数，比如HEAD~100,使用命令：git reset hard+空格+地址
>
> - 从回退到的版本再回退到这个版本之后的版本
>
>   - 输入指令：git reflog
>   - 得到新版本地址之后重新输入指令：git reset hard+空格+地址

### 冲突解决

> - 冲突为什么发生：
>
>   A对代码进行了更改并且提交，但是B不知道，于是B在原版本的基础上也对同一处代码进行了更改
>
> - 解决冲突：
>
>   - 首先选择留下哪个、删掉哪个或者同时都留
>   - 选择好之后重新上传:git add