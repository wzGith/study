1.使用init命令初始化一个git仓库
git init：初始化一个git仓库

2.git原理
git是一个分布式版本管理工具，在分布式网络的节点，每一个节点都具有全部的版本信息，在联网状态可以与远程节点同步或推送本地更新。

3.与svn不同点
svn在服务器建立版本信息，本地只能同步服务器的版本。Git本地即是一个版本库，可以随意创建版本，删除版本，在联网是可以通过命令将本地的修改推送给远程节点

4.git使用前记得设置用户信息
git config --global user.name “wangzhan”
git config --global user.email wangzhan@163.com

5.初始化git仓库后，该目录即为git仓库目录，使用git add命令提交该目录进行的修改。
注意：此处的提交不同于svn的提交，git本地仓库管理当前节点的所有版本及改动，此处提交只是单机操作。
git add test.txt
在本地git仓库根目录新增一个test.txt文件，使用add命令添加该文件

6.使用git commit命令，将进行过add命令的文件提交到本地仓库
git commit -m “提交日志”




