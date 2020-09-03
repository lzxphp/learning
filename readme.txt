第一部分，git简单基本操作
1.git init  命令把这个目录变成git可以管理的仓库
2.git add readme.txt 添加到暂存区里面去
3.git commit -m '提交注释'  把暂存区的所有内容提交到当前分支上
4.git status来查看是否还有文件未提交
5.git diff readme.txt 查看修改了哪些内容，可以作对比
6.git log 查看每次文件修改历史记录
7.git reset --hard HEAD^  回退上一个版本 
7.1 回退到上上个版本只需把HEAD^ 改成 HEAD^^ 以此类推，
     回退具体次数 git reset --hard HEAD~100
8.rm b.txt 删除文件（可恢复）彻底从版本库中删掉了 再执行commit命令
8.1 git checkout -- b.txt   从版本库中恢复  （在未执行commit命令前提）
9. git remote add origin (adress )https://github.com/lzxphp/learning.git 关联远程Git仓库 前提配置好了SSH加密关联
10. git push -u origin master  把本地库的内容推送到远程仓库
11.git clone (adress)https://github.com/lzxphp/learning.git 克隆下载仓库

第二部分 创建与合并分支
1.查看分支：git branch
创建分支：git branch name
切换分支：git checkout name
创建+切换分支：git checkout –b name
合并某分支到当前分支（在主分支上）：git merge name
删除分支：git branch –d name

2.如何解决冲突？分支添加，主分支也添加时，产生会冲突
   Git用<<<<<<<（主），=======（分割），>>>>>>>（分）标记出不同分   支的内容，其中<<<HEAD是指主分支修改的内容，>>>>>dev3 是指dev3上修改的内容，找到位置，手动更改后再push

3.分支策略：
 a.创建一个dev分支。
 b.修改readme.txt内容。
 c.添加到暂存区。
 d.切换回主分支(master)。
 f.合并dev分支，使用命令 git merge –no-ff -m “注释” dev  用–no-ff来禁用”Fast  forward”模式 防止丢失分支信息
 作用总结：首先master主分支应该是非常稳定的，也就是用来发布新版本，
 一般情况下不允许在上面干活，干活一般情况下在新建的dev分支上干活，干完后，比如上要发布，或者说dev分支代码稳定后可以合并到主分支master上来。

第三部分 多人协作
1.git clone 克隆远程的库到本地
2.其他的小伙伴要在dev分支上做开发，就必须把远程的origin的dev分支到本地来
  git checkout –b dev origin/dev
3.git push origin dev

第四部分 删除远程git仓库文件
由于在github上只能删除仓库,却无法删除文件夹或文件, 所以只能通过命令来解决

1.git pull origin master                     # 将远程仓库里面的项目拉下来
2.dir                                               # 查看有哪些文件夹
3.git rm -r --cached file                   # 删除(多次)target文件夹
4.git commit -m '删除了target'         # 提交,添加操作说明
5.git push -u origin master               # 将本次更改更新到github项目上去
注：本地项目中的target文件夹不收操作影响,删除的只是远程仓库中的target,



github更换邮箱 
直接更改github的ssh key.
ssh-keygen -t rsa -C "newemail@xxx.com"