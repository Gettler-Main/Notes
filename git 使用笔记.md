# git 相关命令

## git 初始化

新建一个空文件夹，作为本地仓库

![image-20210812092000603](C:/Users/28599/AppData/Roaming/Typora/typora-user-images/image-20210812092000603.png)

右键该文件夹，选择`Git Bash Here`

输入`git init`对本地仓库进行初始化

## git 配置


输入`git config --list`显示当前的Git配置

输入 `git config user.name 'Gettler'` 配置用户名

输入 `git config user.email 2859902680@qq.com` 配置邮箱

## git clone

输入` git clone https://gitee.com/scoring/scoring.git`对目标项目进行 `clone `下载远程仓库。



## git add/rm/mv

添加文件到暂存区

输入`git add .`添加本地仓库所有变更文件

输入`git add XCX`添加 `XCX` 文件夹及其所有子目录

输入`git rm scoring.sql`删除工作区文件

输入`git mv scoring.sql s.sql`将`scoring.sql`文件重命名为`s.sql`

## git commit

提交暂存区至仓库区

输入`git commit -m’活动详情’`编辑活动详情为提交信息并提交当前暂存区



## git push

推送本地仓库至远程仓库

若本地仓库只有一个分支，仅输入`git push`即可推送

标准命令 `git push https://gitee.com/scoring/scoring master`

# git 操作

只有一个分支的简单同步操作

将远程仓库与本地仓库同步

`git pull`

添加至暂存区

`git add .`

提交至本地仓库

`git commit -m’power’`

推送至远程仓库

`git push`



# git 报错处理方式总结



