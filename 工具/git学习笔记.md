1. 使用init命令初始化一个git仓库
git init：初始化一个git仓库

2. git是什么
git是一个分布式xiangdang版本管理工具，在分布式网络的节点，每一个节点都具有全部的版本信息，在联网状态可以与远程节点同步或推送本地更新。在每个节点都有全部的版本信息，每个节点的内容完全一致，一个节点信息丢失，可以从其他节点处重新获取版本信息

3. 与svn不同点
svn在服务器建立版本信息，本地只能同步服务器的版本。Git本地即是一个版本库，可以随意创建版本，删除版本，在联网时可以通过命令将本地的修改推送给远程节点。svn可以看做是用户与svn服务器间的交互，所有的操作是对服务器的版本信息的修改。git的版本信息在本地，可以看做是一个单机工具，不必关心远程的更新，要发布本地的修改只需将修改的内容往外推送。

4. git使用前记得设置用户信息
git config --global user.name “wangzhan”
git config --global user.email wangzhan@163.com

5. 建立一个git仓库
使用git init可以在本地建立一个git仓库，建立后当前目录生成一个.git文件

6. 向git仓库添加文件
在git仓库目录下新增、删除、修改文件后，使用git add命令将文件添加到git仓库。
git add test.txt
在本地git仓库根目录新增一个test.txt文件，使用add命令添加该文件

7. 一次性add多个文件
git add test1.txt test2.txt test3.txt
或
git add .
或
git add --all

8. 将修改提交到git仓库
使用git commit命令，将所作修改进行提交
git commit -m “提交日志”

9. git add与git commit
在git中有一个暂存区的概念，add是将修改提交到了暂存区，而commit只提交暂存区的内容到版本库
要点：
1.暂存区与版本库有区别，add到暂存区并没有同步到版本库
2.commit命令只会提交暂存区的内容，没有add到暂存区的文件不会提交到版本库
3.可以实现多次add，一次commit

10. git status命令
git status命令用于查看当前git仓库的状态

11. 查看历史提交记录
使用git log命令查看历史提交记录

12. 版本回退
回退到上一个版本：git reset --hard HEAD^
HEAD表示当前版本，HEAD^表示上一个版本，HEAD^^表示上上个版本，往上100个版本可以使用HEAD~100
1.回退到指定版本
使用git log找到该版本的版本号
使用git reset --hard 1094a
hard后面的数字为该版本的版本号（不需要写全，写前几位就行了）
2.回退后又想返回到最新版本
这时候git log已经找不到最新版的版本号了
输入git reflog命令，可以找到历史操作记录，可以从操作记录中找到版本号

13. 撤销本地修改（还没添加到暂存区）
使用git checkout -- test.txt，撤销test.txt的修改，回到上一次add或commit时的状态
能够撤销还没有commit的内容，不能撤销已经add的内容

14. 撤销本地修改（已经添加到暂存区）
使用git reset HEAD test.txt，撤销test.txt的修改，回到上一次commit时的状态
可以撤销已经add的内容

15. 从版本库删除文件
使用git rm test.txt，将test.txt从版本库删除

16. 创建本地sshkey
打开git bash，输入ssh-keygen -t rsa -C “邮件地址”
找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥

17. 本地仓库与远程仓库连接
将本地的公钥添加到github、gitee网站个人账户的sshkey中
git remote add origin git@github.com:wzgith/study.git
将远程仓库与本地仓库建立连接
git push -u origin master
git push origin master
将本地的修改推送到远程仓库（必须将本地公钥添加到github上，才能建立推送）
-u参数仅在第一次推送时使用，远程仓库为空的时候，将本地的master与远程的master关联起来

18. 管理远程库
git remote -v
查看当前远程库的信息
git remote rm origin
删除别名为origin的远程仓库（删除的是绑定关系）
git remote add gitrepo git@github.com:wzgith/study.git
关联远程库

管理本地master与远程master？

19. 从远程库克隆
git clone git@github.com:wzgith/study.git

20. 