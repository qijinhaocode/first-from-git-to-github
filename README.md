# 下载git 并上传本地项目到github
1. windows用户  下载Git软件：https://git-scm.com/downloads![git网站.png](https://img.alicdn.com/imgextra/i1/1860006657/O1CN011DcCTA1z2x9G0fSUS_!!1860006657.png)
2. 安装就是一路next，安装完成后你可以在安装目录下找到git-bash，可以由个人喜好把它放到桌面，git-bash操作命令就是linux的操作命令。 ![git安装目录找到gitbash.png](https://img.alicdn.com/imgextra/i3/1860006657/O1CN01xytmXH1z2x9FwJZ7J_!!1860006657.png)
3.  安装好git后，在命令行或终端中使用下面的命令可以设置git自己的名字和电子邮件。这是因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。
```bash
#在git bash界面输入如下内容即可完成邮箱的注册：
 git config --global user.name "user.name"
#（说明：双引号中需要你的用户名，这个可以随便输入，比如“twodog”）
 git config --global user.email "yourmail@youremail.com.cn"
#（说明： 双引号中需要输入你的有效邮箱，比如“12131312@163.com”）
```
![image](https://img.alicdn.com/imgextra/i1/1860006657/O1CN01qq2U291z2x9GqrTit_!!1860006657.png)
4. 查看是否存在密钥ssh keys
```bash
#命令
 cd ~/.ssh
 ```
5. 如果没设置，就创建新的ssh keys，不然git无法上传文件
```bash
ssh-keygen -t rsa -C "yourmail@youremail.com.cn"
#yourmail@youremail.com.cn 写自己的邮箱
Enter file in which to save the key (/root/.ssh/id_rsa): 
#按Enter 会自动保存在 ~/.ssh 目录下     ~代表home
Enter passphrase (empty for no passphrase): 
Enter same passphrase again:
#以上同样可以用Enter键输入，应该是默认密码
```
![image](https://img.alicdn.com/imgextra/i3/1860006657/O1CN01Ielj9Z1z2x9G0fBr2_!!1860006657.png)

```bash
#这样 操作可以在C:\Users\TWODOG\.ssh 下 生成ssh keys。包括两个文件rd_rsa和id_rsa.pub(llinux 下就在~/.ssh）两种操作系统在git-bash里面都可以用同样的方式打开，当然这不重要，只是告诉你文件在哪。
#[windows ]打开idb_rsa.pub文件、复制内容、打开自己的github，找到Settings-->SSH and GPG keys  粘贴到key里面，点击Add SSH key 具体看下图
```
![image](https://img.alicdn.com/imgextra/i2/1860006657/O1CN019oNDw71z2x9JFaTXu_!!1860006657.png)
![image](https://img.alicdn.com/imgextra/i3/1860006657/O1CN01j2lnJw1z2x9IlesMO_!!1860006657.png)


密钥添加完成，下次在使用时就不需要再添加密钥了。
6. 开始上传本地文件到git上。我们需要先创建一个本地的版本库（其实也就是一个文件夹）。你可以直接右击新建文件夹，也可以右击打开Git bash命令行窗口通过命令来创建。现在我通过命令行在桌面新建一个gittest文件夹（你也可以在其他任何地方创建这个文件夹），并且进入这个文件夹。

![image](https://img.alicdn.com/imgextra/i2/1860006657/O1CN01ewMryr1z2x9HrEEKs_!!1860006657.png)
7. 通过命令把这个文件夹变成Git可管理的仓库
 ```bash
 git init
 ```
 ![image](https://img.alicdn.com/imgextra/i2/1860006657/O1CN016YhC0A1z2x9JFYKUa_!!1860006657.png)
 ![image](https://img.alicdn.com/imgextra/i4/1860006657/O1CN01OXjv391z2x9D41PPj_!!1860006657.png)
 8. 这时候你就可以把你的项目粘贴到这个本地Git仓库里面（粘贴后你可以通过git status来查看你当前的状态），然后通过git add把项目添加到仓库（或git add .把该目录下的所有文件添加到仓库，注意点是用空格隔开的）。在这个过程中你其实可以一直使用git status来查看你当前的状态。如果文件内有东西会出现红色的字，不是绿色，这不是错误。
 ![image](https://img.alicdn.com/imgextra/i4/1860006657/O1CN01MCgelG1z2x98WI7DA_!!1860006657.png)
```bash
#把文件夹下的所有文件添加到仓库
git add .

把项目提交到仓库并添加更新注释
git commit -m "更新注释"
```
![image](https://img.alicdn.com/imgextra/i1/1860006657/O1CN01nqdkLr1z2x9HBihFU_!!1860006657.png)

9.  在Github上创建一个Git仓库。
![image](https://img.alicdn.com/imgextra/i2/1860006657/O1CN01FKCkE61z2x9JFbgOc_!!1860006657.png)
10. 在Github上创建好Git仓库之后我们就可以和本地仓库进行关联了，根据创建好的Git仓库页面的提示，可以在本地仓库的命令行输入
![image](https://img.alicdn.com/imgextra/i3/1860006657/O1CN015vYQh71z2x98WGqF5_!!1860006657.png)
```bash
 # 关联一个github远程仓库 <address>是仓库地址 【请忽略<>】origin是我们命名远程仓库的名字，可以随意取名，但是一般我们看到origin就是远程仓库
git remote add origin <上图复制的地址>
```
![image](https://img.alicdn.com/imgextra/i1/1860006657/O1CN01CHMxcW1z2x9ELcrxD_!!1860006657.png)
```bash
# 由于新建的远程仓库是空的，所以要加上-u这个参数，等远程仓库里面有了内容之后，
git push -u origin master
#下次再从本地库上传内容的时候只需下面这样就可以了：
git push  origin master

```
这时候你再重新刷新你的Github页面进入刚才新建的那个仓库里面就会发现项目已经成功上传了：
![image](https://img.alicdn.com/imgextra/i4/1860006657/O1CN01SZSRxH1z2x9FwKIqd_!!1860006657.png)


---
### 一些坑
你以为完了其实并没有：就是在上面第七步创建远程仓库的时候，如果你勾选了Initialize this repository with a README（就是创建仓库的时候自动给你创建一个README文件），那么到了第九步你将本地仓库内容推送到远程仓库的时候就会报一个to   https://github.com/codetwodog/gittest的错
![image](https://img.alicdn.com/imgextra/i3/1860006657/O1CN01iGfsWs1z2x9IZNdTd_!!1860006657.png)
这是由于你新创建的那个仓库里面的README文件不在本地仓库目录中，这时我们可以通过以下命令先将内容合并以下：
```bash
# 远程仓库与本地合并
git pull --rebase origin master
```
然后再push就可以了


---
## 另一个坑
如果你在提交之后再进行远程仓库和本地合并，会报一个错，，如下图
![image](https://img.alicdn.com/imgextra/i3/1860006657/O1CN018cTvyh1z2x9JFasWH_!!1860006657.png)
```bash
#原因：如果有未提交的更改，是不能git pull的
#解决：
#1.先执行
git stash #可用来暂存当前正在进行的工作
#再执行
git pull –rebase  origin master
git stash pop #从Git栈中读取最近一次保存的内容

```
再进行add 和commit操作就可以了。


---
总结一下：（注意：如果中途弹出输入框让你填写用户名和密码，只需把GitHub的账号和密码填写上即可。）
1. ==在本地创建一个版本库（即文件夹），通过git init把它变成Git仓库。==

2.  ==把项目复制到这个文件夹里面，再通过git add .把项目添加到仓库。==

2.   ==再通过git commit -m "注释内容"把项目提交到仓库。==

4.   ==在Github上设置好SSH密钥后，新建一个远程仓库，通过git remote add origin 仓库url地址将本地仓库和远程仓库进行关联==

5. ==最后通过git push -u origin master把本地仓库的项目推送到远程仓库（也就是Github）上==
6. <font color=red size=6 face=“黑体”>遇到坑看上面</font><table><tr>



