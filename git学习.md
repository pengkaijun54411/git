# GIT学习

```
下载地址：
装包下载地址：https://gitforwindows.org/
直接官网下载也可以：https://git-scm.com/download/win。
```



绑定作者信息：名字和github邮箱

```
git config --global user.name "prngkaijun"
git config --global user.email "pengkaijun@gmail.com"
git config --global --list  查看绑定的信息
```



ssh进行github身份认证

```
ssh-keygen -t ed25519 -C "你的github邮箱"
回车1次，可以设置密码，回车两次不设置密码
id_ed25519你设置的密码

cat ~/.ssh/id_ed25519.pub  查看私有密钥，复制
id_ed25519.pub是ssh私有密钥，要填入github的setting里面的SSH and GPG keys的new SSH key中

ssh -T git@github.com   测试连通性
```





本地新建项目推送到github上

```
git status  看项目状态是否绑定git
git init 初始化git仓库

git add "文件名"    把这个文件加入暂存区
git add .  把本目录所有文件一次性加入暂存区

git commit -m  "备注信息" 将暂存区的内容添加到本地仓库

github上面新建仓库然后复制ssh
git remote add origin  ssh地址   绑定本地仓库和远程仓库
git remote -v  查看远程仓库信息
git push -u origin master  建立本地master和远程master的上下游关系

git log 查看所有提交记录
```

![image-20260911103854593](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20260911103854593.png)

```
1. 工作区 (Working Directory) —— 你的书桌
这是你实际修改文件的地方。你在这里写代码、删删改改。
动作：你在这里编写了新功能或修复了 Bug。

2. 暂存区 (Staging Area) —— 你的待邮寄篮子
当你觉得作业写得差不多了，你会把它放进一个篮子里，准备打包。
关键指令：git add
意义：告诉 Git，这些改动我确认要提交了，先帮我记着。

3. 本地仓库 (Local Repository) —— 你的个人保险箱
你把篮子里的东西打包好，贴上标签（提交信息），快照。
关键指令：git commit
意义：改动正式成为了项目历史的一部分。即便你之后改乱了，也可以随时从这里找回。

4. 远程仓库 (Remote) —— 老师的收件箱（如 GitHub/GitLab）
最后，你把保险箱里的代码通过网络发送给远程服务器，方便其他人查看或合作。
关键指令：git push
意义：备份代码，并与团队共享进度。

知识点说明
git stash (贮藏区)：作业写了一半，突然要改另一个急活，但又不想把没写完的作业提交。这时可以先用 stash 把代码藏进抽屉，等忙完再拿出来继续写（pop）。
git pull (拉取)：看看老师（远程仓库）那里有没有别人交的新作业，直接同步到你的书桌上。
git fetch & merge：先看看远程有什么更新（fetch），确认没问题后再合并（merge）到自己的代码里。
简单总结：
修改代码 → add (放进篮子) → commit (存入箱子) → push (寄给远方)。
```

