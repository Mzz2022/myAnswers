`git merge` 和 `git rebase` 都是用于**分支合并**, 关键在于 commit 记录的处理上不同:

1. `git merge` 会新建一个新的commit对象, 然后两个分支以前的commit 记录都指向这个新的commit记录。这种方法会保留之前每个分支的commit历史
2. `git rebase` 会先找到两个分支的第一个共同的commit祖先记录, 然后将提取当前分支之后的所有commit 记录, 然后将这个commit 记录添加到目标分支的最新提交后面。经过这个合并后, 两个分支合并后的commit 记录就变为了线性的记录了。

<img src="C:\Users\莫松华\AppData\Roaming\Typora\typora-user-images\image-20241125001641293.png" alt="image-20241125001641293" style="zoom: 50%;" />