## GitHub使用

#### Git生成秘钥

- ssh-keygen -t rsa -C "your_email@example.com"

  1. 在Git安装目录存放ssh-keygen.exe程序的usr/bin目录下输入此命令
  2. cd d:/‘Program Files’/Git进入目录，目录名有空格时，bash默认加单引号	

- ```bash
  $ ssh-keygen -t rsa -C "your_email@example.com"
  Generating public/private rsa key pair.
  Enter file in which to save the key
  (/Users/your_user_directory/.ssh/id_rsa): 按回车键
  Enter passphrase (empty for no passphrase): 输入密码
  Enter same passphrase again: 再次输入密码
  ```

  

#### 在GitHub添加公开秘钥

- Git中输入命令，cat ~/.ssh/id_rsa.pub复制秘钥
- GitHub进入Settings的SSH Key添加秘钥
- ssh -T git@github.com 测试使用私人密钥与GitHub通信

#### 创建仓库

- GitHub中New repository
  1. Repository name仓库名称
  2. Description 仓库说明
  3. Public/Private ，Private收费
  4. Initialize this repository with a README,自动初始化仓库并设置README文件，让用户可以立刻clone这个仓库。如果向GitHub添加手中已有Git仓库，建议不勾选，直接手动push
  5. Add.gitignore，初始化时自动生产.gitignore文件，把不需要再Git仓库中进行版本管理的文件记录下来。
  6. Add a license，添加许可协议文件
- 仓库信息说明
  1. README.md文件的内容会自动显示在仓库的首页中，一般标明本仓库所包含的软件概要、使用流程、许可协议等信息。
  2. GitHub Flavored Markdown。在GitHub上进行交流时用到的Issue、评论、Wiki，都可以用Markdown语法表述

#### clone已有仓库

```bash
$ git clone git@github.com:cm22/Hellow-World.git
Cloning into 'Hello-World'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (3/3), done.
$ cd Hello-World
```

​	认证成功后，仓库便会被clone至仓库名后的目录中，将想要公开的代码提交至这个仓库再push到GitHub的仓库中，代码便会被公开。

- 编写代码文件，git status，由于文件还未添加至Git仓库，显示为Untracked files

- 提交，将文件提交至仓库。如此，该文件就进入了版本管理系统的管理之下。今后的更改管理都交由Git进行

  1. ```bash
     $ git add 瑞吉外卖.md
     
     ming.chang@TSJ-004752 MINGW64 /gitRepository/Hellow-World (main)
     $ git commit -m "添加瑞吉外卖项目开发步骤文件"
     
     ```

  2. git log 查看提交日志

#### push

​	执行push，GitHub上的仓库就会被更新

```bash
$ git push
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 2.35 KiB | 1.17 MiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:cm22/Hellow-World.git
 * [new branch]      main -> main
```

如此，代码便在GitHub上公开了