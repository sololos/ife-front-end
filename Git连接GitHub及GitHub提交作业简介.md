# Git连接GitHub及GitHub提交作业简介

### 1、在Windows上安装Git

在Windows上使用Git，可以从Git官网直接[下载安装程序](https://git-scm.com/downloads)，（网速慢的同学可以移步[国内镜像](https://pan.baidu.com/s/1kU5OCOB#list/path=%2Fpub%2Fgit)），然后按默认选项安装即可。
安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！
安装完成后，还需要最后一步设置，绑定你的用户名和邮箱地址，在命令行输入：

    $ git config --global user.name "Your Name"
    $ git config --global user.email "email@example.com"

### 2、在你的电脑创建一个本地版本库

在你的本地磁盘中找一个你认为合适的路径，创建一个空文件夹，这个文件夹名及为你的版本库名
然后点进文件夹中通过 `git init`命令把这个目录变成Git可以管理的仓库，打开 Git Bash,输入命令定位到当前目录：

    $ cd /d/GitHub/ife-front-end

![](https://i.imgur.com/hhY1htu.png)

cd 后面的为你自己的目录路径，然后再输入 : `$ git init` ,返回下面的值及为成功。

    Initialized empty Git repository in /d/GitHub/ife-front-end/.git/

瞬间Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），你可以发现你的目录下多了一个`.git`的目录，如果你没看到，那是因为这个目录默认是隐藏的。
然后你就可以在这个目录下添加你的代码文件或者是作业文件，再通过命令将这些文件推送到GitHub上了，不过在推送之前，先要连接到你的GitHub账户。

### 3、连接到远程仓库GitHub

首先，创建SSH Key。 打开Git Bash ，输入命令：

    $ ssh-keygen -t rsa -C "youremail@example.com"

你需要把邮件地址换成你自己的邮件地址，然后一路回车，使用默认值即可，完成后你可以在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。

其次你要有一个GitHub账号并且登录，打开“settings”，“SSH Keys”页面，然后，点“New SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
![](https://i.imgur.com/ZcikRAU.png)


完成后在右上角找到这个 + 号，New repository 创建一个新的仓库：
![](https://i.imgur.com/lZWHFXv.png)

在`Repository name`填入你的本地仓库名称，`Description`处随便添加点描述这个仓库，其他保持默认设置，点击“Create repository”按钮，就成功地创建了一个新的Git仓库：

![](https://i.imgur.com/J2y0BZe.png)

目前，在GitHub上的这个learngit仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

现在，我们根据GitHub的提示，在本地的仓库下运行命令：

    $ git remote add origin git@github.com:sololos/ife-front-end.git

请千万注意，把上面的`sololos`替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。

下一步，就可以把本地库的所有内容推送到远程库上，你在本地完成的代码或者是作业就全部推送到GitHub上了：

    $ git push -u origin master
    Counting objects: 19, done.
    Delta compression using up to 4 threads.
    Compressing objects: 100% (19/19), done.
    Writing objects: 100% (19/19), 13.73 KiB, done.
    Total 23 (delta 6), reused 0 (delta 0)
    To git@github.com:michaelliao/learngit.git
     * [new branch]  master -> master
    Branch master set up to track remote branch master from origin.

### 4、GitHub提交作业

![](https://i.imgur.com/FPE11SM.png)

代码地址就是你的GitHub仓库的地址

![](https://i.imgur.com/fT1b7uP.png)

而demo地址就要先设置一下你的GitHub Pages ，点`Settings`，拉到下面的`GitHub Pages`，`source`选为`master branch` ，点`save` ：

![](https://i.imgur.com/Cs9rLRG.png)
![](https://i.imgur.com/EbHQsKg.png)

这个链接后面再拼接上相应的页面文件名就是我们要的demo地址。

