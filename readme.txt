learngit
change git

廖雪峰的官方网站

编程
读书
Java教程
Python教程
JavaScript教程
SQL教程
Git教程

    问答

    登录

    目录

    Git教程
    Git简介
    安装Git
    创建版本库
    时光机穿梭
    版本回退
    工作区和暂存区
    管理修改
    撤销修改
    删除文件
    远程仓库
    分支管理
    标签管理
    使用GitHub
    使用码云
    自定义Git
    期末总结

关于作者
时光机穿梭
阅读: 12560474

我们已经成功地添加并提交了一个readme.txt文件，现在，是时候继续工作了，于是，我们继续修改readme.txt文件，改成如下内容：

Git is a distributed version control system.
Git is free software.

现在，运行git status命令看看结果：

$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")

git status命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，readme.txt被修改过了，但还没有准备提交的修改。

虽然Git告诉我们readme.txt被修改了，但如果能看看具体修改了什么内容，自然是很好的。比如你休假两周从国外回来，第一天上班时，已经记不清上次怎么修改的readme.txt，所以，需要用git diff这个命令看看：

$ git diff readme.txt
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.

git diff顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个distributed单词。

知道了对readme.txt作了什么修改后，再把它提交到仓库就放心多了，提交修改和提交新文件是一样的两步，第一步是git add：

$ git add readme.txt

同样没有任何输出。在执行第二步git commit之前，我们再运行git status看看当前仓库的状态：

$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   readme.txt

git status告诉我们，将要被提交的修改包括readme.txt，下一步，就可以放心地提交了：

$ git commit -m "add distributed"
[master e475afc] add distributed
 1 file changed, 1 insertion(+), 1 deletion(-)

提交后，我们再用git status命令看看仓库的当前状态：

$ git status
On branch master
nothing to commit, working tree clean

Git告诉我们当前没有需要提交的修改，而且，工作目录是干净（working tree clean）的。

小结

    要随时掌握工作区的状态，使用git status命令。

    如果git status告诉你有文件被修改过，用git diff可以查看修改内容。

读后有收获可以支付宝请作者喝咖啡：

还可以分享给朋友：

分享到微博
上一页
下一页
评论

发表评论

廖雪峰的官方网站©2019
Powered by iTranswarp
本网站运行在阿里云上并使用阿里云CDN加速。

意见反馈
使用许可

友情链接: 中华诗词 - 阿里云 - SICP - 4clojure

