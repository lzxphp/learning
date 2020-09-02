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
10.git clone (adress)https://github.com/lzxphp/learning.git 克隆下载仓库
