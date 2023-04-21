虚拟机内 Ubuntu20.04 上传笔记的方法

> <font color="yellow">Github中建立空仓库test, 设置为私有private</font>

> <font color="yellow">申请个人访问令牌（personal access token）</font>
> https://blog.csdn.net/HUASHUDEYANJING/article/details/126521798
> <font color="yellow">自2021年8月13日起，github不再支持使用用户名和密码的方式进行push，所以我们最好都用token方式</font>
> 
> 1.首先在GitHub的个人设置页面，找到setting，选择开发者设置Developer setting
> <div align=center>
> <img src="./images/token_1.jpg" style="zoom:100%">
> </div>
> 
> 一直往下拉，找到Developer setting
> <div align=center>
> <img src="./images/token_2.jpg" style="zoom:100%">
> </div>
>
> 2.选择个人访问令牌
> Personal access tokens->Tokens(classic)，
> 然后选中生成令牌
> Generate new token-> Generate new token(classic)
> <div align=center>
> <img src="./images/token_3.jpg" style="zoom:100%">
> </div>
>
> * 输入Note信息、选择Expiration（期限）。我选了90天
> * 选中repo、workflow、delete_repo
> * 点击Generate token
> <div align=center>
> <img src="./images/token_4.jpg" style="zoom:100%">
> <img src="./images/token_5.jpg" style="zoom:100%">
> </div>
>
> 生成token
> <div align=center>
> <img src="./images/token_6.jpg" style="zoom:100%">
> </div>
>
> 保存


> <font color="yellow">接下来，我们将使用token，记得经常更新</font>
> ```html
> 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
> ```
> test私有仓库将可以直接使用token访问（不再需要用户名和密码）
> 格式为：
> ```html
> https://<your_token>@github.com/<USERNAME>/<REPO>.git
> <your_token>：换成你自己得到的token
> <USERNAME>：是你自己github的用户名
> <REPO>：是你的仓库名称
> ```
> 具体如下：
> ```html
> https://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@github.com/ZQuanCheng/test.git
> ```

> <font color="yellow">建立一个专门用来存储仓库的文件夹</font>
> ```html
> $ cd ~/vmshare
> 
> $ mkdir repo
> ```


> <font color="yellow">克隆私有仓库test</font>
> ```html
> cd ~/vmshare/repo
> 
> git clone https://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@github.com/ZQuanCheng/test.git
> ```
> <div align=center>
> <img src="./images/upload_1.jpg" style="zoom:100%">
> </div>
> 


> <font color="yellow">选择需要上传的文件夹/文件，复制到本地仓库 </font>
> （这里是note文件夹）
> <div align=center>
> <img src="./images/upload_2.jpg" style="zoom:100%">
> </div>
> 
> 

> <font color="yellow">更新仓库</font>
> ```html
> $ cd ~/vmshare/repo/test        ### 进入仓库文件夹
>
> $ git add .      ### 添加当前目录下的所有文件到暂存区：
> ```
> 这时候可能有提示（只有第一次会这样）
> <div align=center>
> <img src="./images/upload_3.jpg" style="zoom:100%">
> </div>
>
> 根据提示输入即可git 
> ```html
> $ git config --global --add safe.directory /home/nzq1szh/vmshare/repo/test
> ```
> 再次更新本地仓库
> ```html
> $ git add .      
> ```
> <div align=center>
> <img src="./images/upload_4.jpg" style="zoom:100%">
> </div>
> 
> 不用管这个warning。意思是：CRLF将被LF替换。该文件将在您的工作目录中有其原始的行尾 
>
> 
> 接下来，添加描述信息
> ```html
> $ git commit -m "update"  ### update可以换成别的
> ```
> 这时会在终端显示你要上传所有文件的列表
> <div align=center>
> <img src="./images/upload_5.jpg" style="zoom:100%">
> </div>
>
> 可以看到，图中提示我们config 用户名和邮箱，不用管这个

> 用户信息验证
> 首次使用git时会提醒你输入你的用户邮箱和名字，不用管
> <font color="yellow">自2021年8月13日起，github 不再支持使用用户名和密码的方式进行push，所以我们最好都用 token 方式</font>

> <font color="yellow">本地仓库更新，上传到远程服务器</font>
> 
> token法：直接push
> ```html
> $ git push https://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@github.com/ZQuanCheng/test.git
> ```
> <div align=center>
> <img src="./images/upload_6.jpg" style="zoom:100%">
> <img src="./images/upload_7.jpg" style="zoom:100%">
> </div>
>
> 成功
> 

> <font color="yellow">每次修改完本地仓库后，如何同步到云端？</font>
> ```html
> $ git status                 ### 查看修改的状态
>
> $ git add .                  ### 将改动添加到暂存区
> 
> $ git status                 ### 可以再次查看修改的状态
> 
> $ git commit -m "update"     ### 添加描述信息
> 
> $ git push https://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@github.com/ZQuanCheng/test.git
> 
> ```

> <font color="yellow"> 对于 public 仓库</font>
> * 可以直接git clone
> * 不能直接push，需要token

> <font color="yellow"> 对于 private 仓库</font>
> * 不能直接git clone，需要token
> * 不能直接push，需要token


