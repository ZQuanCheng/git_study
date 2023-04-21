> <font color="yellow"> 将Github的默认分支设置为master，而不是main </font>
> github在2020/10/1宣布上的所有新库都将用中性词【main】命名，取代原来的【master】
> 但是我们都习惯是master，包括很多开源代码
> * Local 本地修改
> <div align=center>
> <img src="./images/master_1.jpg" style="zoom:100%">
> <img src="./images/master_2.jpg" style="zoom:100%">
> </div>
> 
> * Github 远程服务器修改
> <div align=center>
> <img src="./images/master_3.jpg" style="zoom:100%">
> <img src="./images/master_4.jpg" style="zoom:100%">
> </div>
> 

> <font color="yellow"> 更改已有仓库的分支，main更改为master </font>
> Github 远程服务器，可以直接修改默认分支名。但是Local 本地修改后，也无法真正同步，总是有BUG。
> 我们重新建立所有仓库






> <font color="yellow">Github Desktop的几种图形化按钮都对应哪些git命令？</font>
> * commit to main    ### 把改动提交到本地的main分支
> * push origin       ### 把本地的改动同步到服务器
> * Fetch origin      ### 
> * pull origin

> <font color="yellow"> commit to main </font>
> <div align=center>
> <img src="./images/commit_to_main.jpg" style="zoom:100%">
> </div>
>
> 

> <font color="yellow"> push origin </font>
> <div align=center>
> <img src="./images/push_origin.jpg" style="zoom:100%">
> </div>
>
> **push commits to the origin remote**
> You have 1 local commit waiting to be pushed to Github.


> <font color="yellow"> fetch origin </font>
> <div align=center>
> <img src="./images/fetch_origin.jpg" style="zoom:100%">
> </div>
>
> 

> <font color="yellow"> pull origin </font>
> <div align=center>
> <img src="./images/pull_origin.jpg" style="zoom:100%">
> </div>
>
> **Pull 1 commits from the origin remote**
> The current branch（`main`） has commits on Github that do not exist on your machine.
> 

