Git is a version control system.
Git is free software.
Git is a distributed version control system.
Git is free software.
123

$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
$ git add readme.txt
$ git commit -m "wrote a readme file"
$ git status
$ git diff readme.txt 
$ git log
$ git log --pretty=oneline
$ git reset --hard HEAD^
HEAD is now at e475afc add distributed
$ git reset --hard 1094a
HEAD is now at 83b0afe append GPL
$ git reflog
e475afc HEAD@{1}: reset: moving to HEAD^
1094adb (HEAD -> master) HEAD@{2}: commit: append GPL
e475afc HEAD@{3}: commit: add distributed
eaadf4e HEAD@{4}: commit (initial): wrote a readme file
$ git diff HEAD -- readme.txt 
$ git checkout -- readme.txt
$ git reset HEAD readme.txt
git reset HEAD <file>可以把暂存区的修改撤销掉（unstage），重新放回工作区
$ git checkout -- readme.txt
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。
$ rm test.txt
现在你有两个选择，一是确实要从版本库中删除该文件，那就用命令git rm删掉，并且git commit：
$ git rm test.txt
rm 'test.txt'

$ git commit -m "remove test.txt"
[master d46f35e] remove test.txt
 1 file changed, 1 deletion(-)
 delete mode 100644 test.txt
 另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本：
git checkout其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。
$ git checkout -- test.txt
$ ssh-keygen -t rsa -C "youremail@example.com"
第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：

然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
现在，我们根据GitHub的提示，在本地的learngit仓库下运行命令：

$ git remote add origin git@github.com:michaelliao/learngit.git

请千万注意，把上面的michaelliao替换成你自己的GitHub账户名，否则，你在本地关联的就是我的远程库，关联没有问题，但是你以后推送是推不上去的，因为你的SSH Key公钥不在我的账户列表中。
添加后，远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。

$ git remote add origin git@github.com:sunzhe6/test.git
$ git remote rm origin
$ git push -u origin master
提示： “ssh:connect to host github.com port 22: Connection timed out”
cd ~/.ssh
vim config
Host github.com
User git
Hostname ssh.github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa
Port 443

Host gitlab.com
Hostname altssh.gitlab.com
User git
Port 443
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_rsa

    检查是否成功

ssh -T git@github.com