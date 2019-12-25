一.配置操作
1.设置用户信息
git config --global user.name  "name"
git config --global user.email "email"
2.0x80以上字符进行quote
git config --global core.quoepath false
3.创建SSH Key
ssh-keygen  -t rsa –C "email"
-t密钥类型
-C 指明 "email" 是用于识别密钥的备注
email实际只是个备注内容随便
之后运行输入passphrase(用于clone时的密码)
最后是设置生成添加位置
创建SSH Key内容均无测试
二.基础使用操作
1.创建管理仓库
git init
2.查看仓库状态
git status
3.比较暂存区与工作区的差异
git diff filename
4.查看所有提交过的版本信息
git log
git log --pretty=oneline
5.查看所有分支的所有操作记录
git reflog
6.回退版本
git reset --hard head^
git reset --hard head^^
git reset --hard head~1
git reset --hard head~100
git reset --hard 5b06dae
7.查看文档内容
cat filename
8.本地Git仓库添加至Git仓库
 1> 在github账号中添加本地的SSH Key
 登录->Settings->SSH and GPS keys->New SSH key->将本地id_rsa.pub文件的内容拷贝进去
 2> 创建一个对应的仓库
 new repository->设置相关项
 3> 在本地git上运用github上仓库的链接关联
 git remote add origin https://github.com/Rick-Li-0-0/StudyGit.git
 比较内容发现链接为仓库HTTP地址加后缀.git(推测)
 添加仓库之间的关联
 git push -u origin master
 git push origin master
 将本地master推送到远程
 -u 将本地master分支内容推送到远程新的master分支，并将本地和远程的master分支关联起来
 (-u 将本地的master分支推送到origin主机，并指定origin为默认主机
 之后可直接使用git push进行推送)
 4> 输入自己github账号与密码
9.从远程克隆一个本地库
git clone https://github.com/Rick-Li-0-0/StudyGit.git
将远程库克隆到当前目录下
2.分支与暂存区
 分支                             | 暂存区
 1> git commit -m "提交的注释"    | 1> git add filename
 将缓存区内容提交至当前分支       | 将filename文件更改内容添加暂存区
 2> git branch                    | 更改内容包括删除文件
 查看当前所有分支                 | 2> git checkout -- filename
 3> git branch dev                |    git checkout filename 
 创建名为dev的分支                | 将filename内容撤销至暂存区中filename内容相同
 4> git branch -d dev             | 可用于删除后恢复于修改后还原文件
 删除dev分支                      |
 5> git checkout dev              | 
 切换到名为dev的分支上去          |
 6> git checkout -b dev           |
 创建并切换到名为dev的分支上      |
 7> git merge dev                 |
 将dev分支合并到当前分支上        |
 此后将删除分支信息               |
三.git概念
1.工作区
.git隐藏文件夹同级目录下的所有文件
2.版本库
.git文件夹。里面包含了很多信息，如暂存区，分支等信息。