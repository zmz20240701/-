- `git add <文件名>` 将文件加入缓存区

- `git add . ` 将整个文件夹加入缓存区

- `git commit -m "<message>" <文件名>` 将文件提交版本

- `git commit -m "<message>"` 将整个文件夹提交版本

只有缓存区的内容才能提交版本

message 的内容要简明扼要, 方便后续查看时能回想起文件做了什么变化

-  `git reflog` 查看提交版本的历史, 版本号可以用于在版本之间穿梭

- `git checkout <版本号>` 穿梭到指定的版本

- `git switch <分支名>` 转到指定的分支

在穿梭到特定版本之前, 当前版本的变化需要处理, 否则不允许穿梭

- `git stash` 如果你当前的更改还不想提交，但也不想丢失，可以将这些更改暂存起来

- 然后就可以切换版本了

- 如果你之后想恢复之前暂存的更改，可以执行：`git stash pop`

- 或者你觉得不想要当前版本的变化了, 想直接穿梭到指定版本, 可以将当前版本的变化丢弃, 恢复到上次提交的状态

- `git restore .`

如果你想恢复到之前的版本

`git restore --source=<版本号> `

恢复之后, 你可能觉得还是老版本好, 可以将其作为一个新版本来提交:
git add <文件路径>
git commit -m "恢复 <文件路径> 到某个版本"


# 添加 SSH 秘钥

每次更新到不同的GitHub 账户时, 都要在终端生成 ssh 秘钥,并将ssh 公钥添加到 GitHub

1. 生成 ssh 秘钥 

` ssh-keygen -t rsa -C "你的邮箱"`

2. 生成的秘钥文件在 `~/.ssh` 目录下

注意这里的rsa 是加密算法, 你可以选择其他的加密算法, 文件名为 `id_<加密算法>.pub`

3. 添加 ssh 秘钥到 ssh-agent

`eval "$(ssh-agent -s)"`
`ssh-add ~/.ssh/id_rsa`

4. 将 ssh 公钥添加到 GitHub

`cat ~/.ssh/id_rsa.pub`

复制公钥内容, 粘贴到 GitHub 的 ssh 设置中

5. 登录到你的 GitHub 账户，进入 Settings -> SSH and GPG keys -> New SSH key。

6. 将复制的公钥粘贴到 GitHub 的 SSH key 输入框中，并保存。

7. 确保你的 SSH 密钥已正确添加到 GitHub 后，你可以使用 SSH URL 进行 Git 操作，例如

`git remote set-url origin git@github.com:zmz20240701/RESTAPI.git`

添加完成以后, 你就可以直接使用 git 命令进行操作了

`git push -u origin main`