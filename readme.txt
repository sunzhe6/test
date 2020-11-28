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
git reset HEAD <file>���԰��ݴ������޸ĳ�������unstage�������·Żع�����
$ git checkout -- readme.txt
����1����������˹�����ĳ���ļ������ݣ���ֱ�Ӷ������������޸�ʱ��������git checkout -- file��

����2�����㲻�������˹�����ĳ���ļ������ݣ�����ӵ����ݴ���ʱ���붪���޸ģ�����������һ��������git reset HEAD <file>���ͻص��˳���1���ڶ���������1������

����3���Ѿ��ύ�˲����ʵ��޸ĵ��汾��ʱ����Ҫ���������ύ���ο��汾����һ�ڣ�����ǰ����û�����͵�Զ�̿⡣
$ rm test.txt
������������ѡ��һ��ȷʵҪ�Ӱ汾����ɾ�����ļ����Ǿ�������git rmɾ��������git commit��
$ git rm test.txt
rm 'test.txt'

$ git commit -m "remove test.txt"
[master d46f35e] remove test.txt
 1 file changed, 1 deletion(-)
 delete mode 100644 test.txt
 ��һ�������ɾ���ˣ���Ϊ�汾���ﻹ���أ����Կ��Ժ����ɵذ���ɾ���ļ��ָ������°汾��
git checkout��ʵ���ð汾����İ汾�滻�������İ汾�����۹��������޸Ļ���ɾ���������ԡ�һ����ԭ����
$ git checkout -- test.txt
$ ssh-keygen -t rsa -C "youremail@example.com"
��2������½GitHub���򿪡�Account settings������SSH Keys��ҳ�棺

Ȼ�󣬵㡰Add SSH Key������������Title����Key�ı�����ճ��id_rsa.pub�ļ������ݣ�
���ڣ����Ǹ���GitHub����ʾ���ڱ��ص�learngit�ֿ����������

$ git remote add origin git@github.com:michaelliao/learngit.git

��ǧ��ע�⣬�������michaelliao�滻�����Լ���GitHub�˻������������ڱ��ع����ľ����ҵ�Զ�̿⣬����û�����⣬�������Ժ��������Ʋ���ȥ�ģ���Ϊ���SSH Key��Կ�����ҵ��˻��б��С�
��Ӻ�Զ�̿�����־���origin������GitĬ�ϵĽз���Ҳ���Ըĳɱ�ģ�����origin�������һ����֪����Զ�̿⡣

$ git remote add origin git@github.com:sunzhe6/test.git
$ git remote rm origin
$ git push -u origin master
��ʾ�� ��ssh:connect to host github.com port 22: Connection timed out��
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

    ����Ƿ�ɹ�

ssh -T git@github.com