# Permission denied (publickey). Could not read from remote repository

客户端与服务端未生成 ssh key
客户端与服务端的ssh key不匹配

## git终端的配置

### 1.ssh-keygen -t rsa -C "2358198282@qq.com"  

Enter ...

### 2.ssh -v git@github.com

### 3.ssh-agent -s 

### 4.ssh-add ~/.ssh/id_rsa (若不行，下面两部)
### 5.ssh-agent bash

### 6.ssh-add ~/.ssh/id_rsa

## gitub的配置

###  settings => SSH and GPG keys =>  new SSH key (复制id_rsa.pub)

## 验证
ssh -T git@github.com 