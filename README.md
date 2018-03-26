# hello Github

## 从电脑往github上传文件，需要两步
1. 注册好的你Gihub账号,下载好github客户端，不多说明记录。
2. 在github网站上的用户setting里添加你电脑的SSH key了---让github账号信任电脑设备
  ### 步骤：
  - 说明：就是在电脑生成一个ssh公钥，复制到你的github账号setting-->SSH and GPG keys中，用于加密通信
  - a 设置Git的user name和email：
     
        git config --global user.name "name"
      
        git config --global user.email "email@gmail.com"

      ##### 调出输入命令的界面：文件夹上右键，点Git Bash Here，会出现cmd界面，下面的命令必须在这个界面才能执行。具体学习git相关

  - b 生成SSH密钥过程：
      
        查看是否已经有了ssh密钥：cd ~/.ssh  （如果没有密钥则不会有此文件夹，有则备份删除）
        
        生存密钥：ssh-keygen -t rsa -C “email@gmail.com”    （ 按3个回车，密码为空。）

        最后得到了两个文件：id_rsa和id_rsa.pub

  - c 在github上添加ssh密钥，这要添加的是“id_rsa.pub”里面的公钥。

        你的github首页-->右上角头像-->setting-->SSH and GPG keys-->new一个sshkey，把上面的公钥复制到key，title可不填

## gitbub中建仓库repositories，从github网站clone项目到本地，不多说明记录

### 准备好你自己需要放在git的文件夹 获取源码：

    git clone git@github.com:galabug/hello-github.git

- 这样你的机器上就有一个repo了。

### git于svn所不同的是git是分布式的，没有服务器概念。所有的人的机器上都有一个repo，每次提交都是给自己机器的repo

-  仓库初始化：
   
    git init

-  生成快照并存入项目索引等待commit：
    
    git add

-  文件,还有git rm,git mv等等…

-  项目索引提交：
  
    git commit

## 做好上面的准备，上传文件到github  push

### 协作编程：

  将本地repo于远程的origin的repo合并，

-  推送本地更新到远程：

    git push origin master

-  更新远程更新到本地：

    git pull origin master

  补充：
  - 添加远端repo：

      $ git remote add origin git@github.com:galabug/helloWorld.git

  - 删除原有的链接方式

      $ git remote rm origin


### 初始用到的命令

    $ git add .   （把所有修改加入）

    $ git commit -m "commit my project"

    $ git push -u origin master

### 记录问题：每次push都要密码，是用了https的方式链接项目，改用ssh方式解决问题

  1.查看链接方式

    $ git remote -v

  2.删除原有的链接方式

    $ git remote rm origin

  3.重新添加ssh方式的链接方式

    $ git remote add origin git@github.com:galabug/helloWorld.git

# 需要继续学习的东西
## 1. git
## 2. markdown 语法
## 3. 查看html--的方式
   - 进入html所在的项目Repository
   - 进入setting--->GitHub Pages--->Theme Chooser, 随便选一个主题
   - 选完主题后，就会把你这个工程发布，并在GitHub Pages下面生成一个地址
   - Your site is published at https://galabug.github.io/hello-github/
   - 这个地址进去就是README.md页面，然后后面可以接对应的html文件地址，能呈现出html页面

