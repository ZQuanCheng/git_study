# Git 学习

### 一个图形化的学习网站
> https://learngitbranching.js.org/?locale=zh_CN
> 
> Git的本质是命令行，因此理解起来有难度。如果是图形界面，就会容易理解。
> 
> 所以这个学习git的网站非常不错
> 
> 可以从最基本的git commit开始学习起来
> 
> 真正好的教程并不是几十集一下子扔给你、
>


### Bosch实习期间学会的操作

> <font color="yellow">`clone`仓库</font>
>
> ```bash
> $ git clone ssh://git@sourcecode01.de.bosch.com:7999/pjw3/pj_w3-root.git
> 
> $ git fetch         ### 更新库信息
> 
> $ git branch   ### 查看当前分支
> 
> $ git checkout <branch_name>         # 切换到已有分支
> 
> $ git checkout -b <new_branch_name>  # 创建并切换到新分支
> 
> $ git submodule update --init --recursive   ### 更新子模块
> # 注意看.gitmodules中的链接是否正确
> ```
> 疑问，安装`~/aos-conan/aos2_4`时，有如下命令
> 
> ```bash
> $ cd ~/intern/pj_w3-root/mw/aos-workspace
> 
> $ git branch 
> # 查看分支是否为 MWAOS_2303.2.4_release
> # 如果不是,执行
> $ git checkout MWAOS_2303.2.4_release -b MWAOS_2303.2.4_release
> ```
>
> 这里的`git checkout MWAOS_2303.2.4_release -b MWAOS_2303.2.4_release`格式不符合`git checkout -b <new_branch_name>`, 在`-b`前还有参数。
> 这里是`git checkout <branch_name>`和`git checkout -b <new_branch_name>`合并了吗
>
> 

> <font color="yellow">本地拉取远程分支</font>
> 
> ```bash
> $ cd ~/intern/Unittest/Driving/pj_w3-root/asw/fct
> 
> $ git branch # 查看当前分支为branch
>  
> $ git pull # 拉取远程分支
> 
> $ git checkout feature/CNWVIII-39246-fct-fct-pi2306-unit-test-development-demo
> 
> $ git branch # 查看当前分支为branch
> ```
> 


> <font color="yellow">本地修改后，提交到远程仓库</font>
> 
> ```bash
> $ git status                 ### 查看修改的状态
> 
> $ git add .                  ### 将改动添加到暂存区
> 
> $ git status                 ### 可以再次查看修改的状态
> 
> $ git commit -m "update"     ### 添加描述信息
> 
> $ git push <远程主机名> <本地分支名>:<远程分支名>
> # 如果本地分支名与远程分支名相同，则可以省略冒号：
> $ git push <远程主机名> <本地分支名>
> ```
>
> 注：如果是`Github`仓库
> `Github`仓库更新后提交时，通过`ssh`密钥来上传（由`Github`账号创建）
> ```bash
> $ git push https://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@github.com/ZQuanCheng/test.git
> ```
> 


> `Yang Tian`姐用到的`git`命令
> 
> ```bash
> 
> git stash show
> 
> git stash
> 
> git pull
> ```
> 




### 复习之前学过的知识 <Git的安装及使用.docx>

> 






















