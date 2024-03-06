---
title: "【git】 ssh: connect to host github.com port 22: Connection timed out 的解决方法"
date: 2024-01-22 17:51:55
urlname: debug1-git-ssh-problem
tags: debug
description: 问题的原因在于防火墙屏蔽了22端口，切换成443端口就可以解决这个问题。
---

```
> git pull --tags origin main
ssh: connect to host github.com port 22: Connection timed out
fatal: Could not read from remote repository.
 
Please make sure you have the correct access rights
and the repository exists.
```

问题的原因在于防火墙屏蔽了22端口，切换成443端口就可以解决这个问题。


第一步：在终端中输入以下命令：

```
ssh -T -p 443 git@ssh.github.com

#返回结果： Hi Jye10032! You've successfully authenticated, but GitHub does not provide shell access.
```


这个命令的意思是：使用SSH，通过443端口，连接到ssh.github.com服务器，用户名为git，并且不分配一个伪终端。

-p 443：这个选项告诉SSH使用443端口来连接到远程服务器。默认情况下，SSH使用22端口，但有些网络环境可能会阻止22端口的连接。443端口是HTTPS的默认端口，通常不会被阻止。


第二步：在 C盘->用户->用户名文件夹 下找到.ssh文件夹，创建config文件并输入以下内容：

```
Host github.com
    Hostname ssh.github.com
    Port 443
```



第三步：git push 重新推送，推送成功
