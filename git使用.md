# git使用

## 基于GitHub（Linux系统）

#### 创建本地仓库

1. 创建一个本地文件夹   切换到新建文件夹   即为工作区
2. 在本地文件夹创建一个本地仓库  git init

#### 添加暂存区

* git add 本地代码文件        #将文件添加到暂存区
* git add .  是将所有文件都添加到暂存区

#### 配置用户名和邮箱

* git config user.name "配置用户名"（区分责任人）
* git config user.email "配置邮箱"（翻遍联系作者）

#### 提交到本地仓库

* git commit -a -m '这次提交的备注信息'

#### 绑定远程仓库地址

* git remote add origin  +远程仓库地址
* git remote rm origin  # 取消跟仓库的绑定

#### 提交到远程仓库

* git pull origin master #提交到github的master分支
* 解决冲突  --allow=unrelated-histories  允许不匹配的提交
* git push origin master
* 账号密码

### ssh  生成密钥对免密码

> https每次提交的时候 都要输入用户名和密码   ssh 首次需要将本地的密钥提交给远程仓库  获得 允许  下次就不需要输入用户名和密码

* 首先删除其他的仓库绑定
  * git remote rm origin
* 重新绑定ssh
  * git remote add origin  +远程仓库地址

* 先在工作区创建 ssh key
  * 教程 https://docs.github.com/en/free-pro-team@latest/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
  * ssh-keygen -t rsa -b 4096 -C "hengheng@gmail.com" #生成密钥对
    * 自己指定密钥文件名
  * cd /root/.ssh 到此查看密钥对
    * cat id_rsa.pub  # 查看密钥
* 将这个密钥对提交到远程仓库
  *  \#将这个密钥提交给远程仓库  https://github.com/settings/keys  来到远程仓库 点击settings ssh and GPGkeys    添加 SSH keys 

给i他