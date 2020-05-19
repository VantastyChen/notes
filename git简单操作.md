## **只有自己一个人进行的项目开发**

1. Github 创建一个仓库 (new 一下，gui操作就不细说了)
2. 默认会有一个分支 master

```text
//打开本地所需要的文件下，terminial 进行init
git init 
git add README.md //比如add一个readme
git commit -m 'readme'
git remote add origin <仓库地址>
git push origin master //将本地仓库master和远程仓库master建立连接 
```

之后你每次想要修改之前

```text
git pull //从远程仓库把东西拉下来，保证目前手上的是最新的

-- 一顿操作进行修改以后

git add .
git commit -m 'update'
git push //因为只有一个分支，直接git push就行了，会push到远程仓库的master中
```



## **与别人合作项目**

1. Github创建一个仓库(这就不介绍了)， 此时默认的一个分支是master
2. git init和上面是一样的
3. 在本地再创建一个自己开发的本地分支，比如named as dev

建立起本地dev与远程dev的连接

```text
git branch dev  //在本地创建一个dev分支
git checkout dev //在本地切换到dev分支
git add .
git commit -m 'try add branch'
git remote add origin <仓库地址>
git push origin dev //将本地仓库dev和远程仓库dev建立连接

--你平时开发就在你本地的dev修改你的代码，git pull, add ,commit， 
-- git push origin dev 这样也是push到远程你的dev分支，不会影响到主分支master

当你dev开发完毕，想要merge到主分支master上时

git checkout master  //本地切换到master分支
git pull // 将远程仓库的数据拉下来，保证目前是最新的数据
git merge dev //将dev分支合并到master上 有conflict就去解决冲突咯
git commit -m '说明' 
git push //将本地master push到远程master
```