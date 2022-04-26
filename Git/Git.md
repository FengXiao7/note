![image-20220423161037156](https://picture-feng.oss-cn-chengdu.aliyuncs.com/img/image-20220423161037156.png)

我们的本地库还可以push至远程仓库

# 常用命令

## 1.设置用户

git config --global user.name  用户名 设置用户签名 
git config --global user.email  邮箱 设置用户签名 

这两个命令一般只设置一次就够了

![image-20220423161450248](C:\Users\FengXiao7\AppData\Roaming\Typora\typora-user-images\image-20220423161450248.png)

## 2.初始化

git init 初始化本地库 

初始化完毕后会出现一个.git的隐藏文件夹

## 3.查看本地库状态 

git status 

## 4.添加到暂存区 

git add  文件名 

git add .会提交所有文件

## 5.提交到本地库 

git commit -m "日志信息"  文件名 提交到本地库 

不加-m，也会让你输提交信息

## 6.查看历史记录 

git reflog 简略历史记录

git log  详细历史记录

查看详细历史记录，按q退出查看



## 7.版本穿梭

git reset --hard  版本号 版本穿梭 

这里的版本号就是我们git reflog简略历史记录里的7位字符串

## 8.分支操作

git branch  分支名 			创建分支 
git branch -v 					 查看分支 
git checkout  分支名 		切换分支 
git merge  分支名 			把指定的分支合并到当前分支上，如果有冲突需要手动判断下

删除分支

传送门：[(26条消息) git 命令怎么删除本地分支_凯小默：树上的男爵的博客-CSDN博客_git删除本地分支命令](https://blog.csdn.net/kaimo313/article/details/122371144)

## 9.远程库操作

git remote -v 													  查看当前所有远程地址别名 
git remote add  别名  										 给远程地址起别名 
git push  别名  分支 										   推送本地分支上的内容到远程仓库 
git clone  远程地址 											将远程仓库的内容克隆到本地 
git pull  远程库地址别名  远程分支名 				将远程仓库对于分支最新内容拉下来后与当前本地分支直接合并 



没起别名时，git remote -v看不见任何别名。

但如果是clone下来的仓库，git remote -v可以看见一个默认别名origin