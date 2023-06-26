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
> $ git stash show
> 
> $ git stash
> 
> $ git pull
> ```
> 



>
> 对于已有的分支，可以这样切换
> 
>
> ```bash
> $ git switch <branch_name>
> ```
> 
> <div align=center>
> <img src="./images/git_switch.png" style="zoom:80%">
> </div>
>
> 

> 
>
> ```bash
> $ git log # 当前分支中，看看都是什么人提交过更新
> ```
>
> 当前分支的提交记录
> 



> 
>
> ```bash
> $ git merge <branch_name> # branch_name: 合并到当前分支的目标分支名称
> ```
>
> 一般都用`merge`, 不用`rebase`
>
> https://blog.csdn.net/All_In_gzx_cc/article/details/125482617
>
> 




> 
>
> ```bash
> $ git rebase <branch1_name> <branch2_name> # 当前分支是分支1的子分支，我们把分支1的子分支，移动到分支2下面
> ```
>
> 总体来说，即使是单机也不建议使用。
>
> https://blog.csdn.net/weixin_42310154/article/details/119004977
>
> 大部分公司其实会禁用`rebase`，不管是拉代码还是push代码统一都使用`merge`，虽然会多出无意义的一条提交记录“`Merge … to …`”，但至少能清楚地知道主线上谁合了的代码以及他们合代码的时间先后顺序
> 
> 





#### `Bosch - develop`

> 
> `root`下的分支为`develop_aos_0.14.0`, `FCT`下的分支为`develop`
> 
> 我是在`develop`上做的`UT`，我创建的子分支为`feature/CNWVIII-39246-fct-fct-pi2306-unit-test-development-zqc`
>
> <font color="yellow">本地拉取</font>
> 
> ```bash
> $ cd ~/intern/Unittest/workspace/pj_w3-root/asw/fct
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
> <font color="yellow">添加`UT`代码，编译</font>
> 
> ```bash
> $ git switch feature/CNWVIII-39246-fct-fct-pi2306-unit-test-development-demo # 在develop分支的子分支中写Unit Test
> 
> $ source ../../mw/aos-workspace/prepare_ws.sh
> 
> $ ./fct_build.sh -t debug
> ```
> 
> 
> <font color="gree">但是我们花了一段时间写完`UT`后，可能有人更新的`develop`分支，我们要确保最新的分支也可以编译通过</font>
> 
> ```bash
> $ git switch develop # 转换到develop分支
> 
> $ git pull # develop分支更新到最新版本
> 
> $ git submodule update --init --recursive   ### 更新子模块
> 
> $ git switch feature/CNWVIII-39246-fct-fct-pi2306-unit-test-development-demo # 回到到develop分支的子分支
> 
> $ git merge develop # 将develop的最新内容merge到子分支上
> # 这时候可能会进入一个界面，不用管 ，退出
> 
> $ git submodule update --init --recursive   ### 更新子模块
> 
> $ git log # 看看都是什么人提交过更新
> # 按q退出
> ```
> <font color="gree">注意要：最新`develop`分支对应的`conan`版本是`5.3.3`，需要同步更新</font>
> 
> 新建`~/aos-conan`，用于存放不同版本的aos环境配置
> 新建`~/aos-conan/aos5_3_3`
> 
> 运行`install.sh`脚本
> 
> ```bash
> $ cd ~/intern/pj_w3-root/mw/aos-workspace
> 
> $ git branch 
> # 查看分支是否为 MWAOS_2305.3.3_release
> # 如果不是, 执行下面的命令
>  
> $ git pull # 拉取远程分支
> 
> $ git checkout MWAOS_2305.3.3_release -b MWAOS_2305.3.3_release
> 
> $ ./install.sh -c ~/aos-conan/aos5_3_3
> # $ sudo ./install.sh -c ~/aos-conan/aos5_3_3
> ```
> 
> 
> <font color="gree">重新编译一遍`develop`分支下的`FCT`仓库，确保没有问题</font>
>
> ```bash
> $ git switch develop # 转换到develop分支
> 
> $ source ../../mw/aos-workspace/prepare_ws.sh
> 
> $ ./fct_build.sh -t debug
> ```
> 
> <font color="gree">重新编译一遍`feature/CNWVIII-39246-fct-fct-pi2306-unit-test-development-demo`子分支下的`FCT`仓库，确保没有问题</font>
>
> ```bash
> $ git switch feature/CNWVIII-39246-fct-fct-pi2306-unit-test-development-demo # develop分支的子分支
> 
> $ source ../../mw/aos-workspace/prepare_ws.sh
> 
> $ ./fct_build.sh -t debug
> ```
> 
> <font color="yellow">编译通过后上传</font>
> 
> ```bash
> $ git add .
> 
> $ git status
> 
> $ git commit -m "CNWVIII-39246 unit_test"
> 
> $ git push
> ```
>
> <font color="yellow">`push`到子分支后，申请`merge`到`develop`分支</font>
>
> https://rb-tracker.bosch.com/tracker08/browse/CNWVIII-39246
> 
> 











### 复习之前学过的知识 <Git的安装及使用.docx>

> 






















