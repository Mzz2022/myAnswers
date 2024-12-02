1. `git clone` 到本地

2. 创建本地新分支 `git checkout -b xxx`(新分支名称)

3. `git diff` 查看修改内容

4. `git add <change_file>` 添加内容到暂存区

5. `git commit` 

6. `git push origin xxx `提交本地仓库xxx分支内容到GitHub

   ------

   (如果在写自己的代码过程中发现远端GitHub上代码出现改变)

7. `git checkout main` 切换本地分支到main

8. `git pull origin master` 将元的修改过的代码再更新到本地

9. `git checkout xxx` 回到xxx分支

10. `git rebase main` 我在xxx分支上, 先把买main移过来, 然后根据我的commit来修改成新的内容

    (中途可能会出现, rebase conflict ---- 手动选择保留哪段代码)

11. `git push -f origin xxx` 把rebase后并将更新过的代码再push到远端的GitHub上(-f 表示强行force)
12. 原项目主人采用`pull request` 中的 `squash and merge` 合并所有不同的commit

------

​	(远端完成更新后)

13. `git branch -d xxx` 删除本地的xxx分支
14. `git pull origin master` 再把远端的最新代码拉至本地