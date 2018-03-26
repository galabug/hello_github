# helloWorld 
## 想要在github上传文件，首先要准备两个东西
1. 注册好的你Gihub账号
2. 在setting里的SSH里有你电脑的SSHKey了。
  - 让github账号信任电脑设备，允许上传文件，在本电脑生成一个公钥，
  - 设置Git的user name和email：
    git config --global user.name "name"
    git config --global user.email "email@gmail.com"
  - 生成SSH密钥过程：
  1.  查看是否已经有了ssh密钥：cd ~/.ssh
        如果没有密钥则不会有此文件夹，有则备份删除
    2.  生存密钥：
      ssh-keygen -t rsa -C “email@gmail.com”
      按3个回车，密码为空。

      >Your identification has been saved in /home/tekkub/.ssh/id_rsa.
      >Your public key has been saved in /home/tekkub/.ssh/id_rsa.pub.
      >The key fingerprint is:

      最后得到了两个文件：id_rsa和id_rsa.pub
    4. 在github上添加ssh密钥，这要添加的是“id_rsa.pub”里面的公钥。
3. 准备好你自己需要放在git的文件夹
1. 获取源码：
  git clone git@github.com:galabug/helloWorld.git

2. 这样你的机器上就有一个repo了。

3. git于svn所不同的是git是分布式的，没有服务器概念。所有的人的机器上都有一个repo，每次提交都是给自己机器的repo

  仓库初始化：
  git init

  生成快照并存入项目索引：
  git add

  文件,还有git rm,git mv等等…

  项目索引提交：
  git commit

4. 协作编程：
  将本地repo于远程的origin的repo合并，

  推送本地更新到远程：
  git push origin master

  更新远程更新到本地：
  git pull origin master
  补充：
  添加远端repo：
  $ git remote add upstream git@github.com:galabug/helloWorld.git

  重命名远端repo：
  $ git@github.com:galabug/helloWorld.git为“upstream”


5. 初始用到的命令

   - $ git commit -m "commit my project"
   - $ git push -u origin master

  ### 记录问题：每次push都要密码，是用了https的方式链接项目，改用ssh方式解决问题

  1.查看链接方式
   - $ git remote -v

  2.删除原有的链接方式
   - $ git remote rm origin

  3.重新添加ssh方式的链接方式
   - $ git remote add origin git@github.com:galabug/helloWorld.git