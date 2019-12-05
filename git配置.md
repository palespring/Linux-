# Git 环境的配置与搭建（SSH）

## 背景

当有多个git账号时，比如：

- 一个gitee，用于公司内部的工作开发；
-  一个github，用于自己进行一些开发活动；

## 解决办法

1. 生成对应的SSH-KEY

    ` ssh-keygen -t rsa -C 'xxxxx@company.com' -f ~/.ssh/文件前缀_id_rsa`

2. 在 ~/.ssh 目录下新建一个config文件，添加如下内容（其中Host和HostName填写git服务器的域名，IdentityFile指定私钥的路径）

    ```
    # gitlab
    Host git.deya
    HostName 192.168.1.65
    Port 6000
    PreferredAuthentications publickey
    IdentityFile ~/.ssh/gitlab_id_rsa
    ```
