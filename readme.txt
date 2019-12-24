一.配置操作
1.设置用户信息
git config --global user.name  "name"
git config --global user.email "email"
2.0x80以上字符进行quote
git config --global core.quoepath false
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
2.分支与暂存区
 分支                             | 暂存区
 1> git commit -m "提交的注释"    | 1> git add filename
 将缓存区内容提交至当前分支       | 将filename文件更改内容添加暂存区
                                  | 更改内容包括删除文件
                                  | 2> git checkout -- filename
                                  |    git checkout filename 
                                  | 将filename内容撤销至暂存区中filename内容相同
                                  |
                                  |
                                  |
                                  |
                                  |
                                  |
三.git概念
1.工作区
.git隐藏文件夹同级目录下的所有文件
2.版本库
.git文件夹。里面包含了很多信息，如暂存区，分支等信息。