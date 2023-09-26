## 1 创建key

```shell
ssh-keygen -t rsa -C "xxxxxx@company.com” -f ~/.ssh/id-rsa
```



## 2. 使用指定的Key

方式一： 编辑 .ssh

```shell
Host github.com #git项目里面的域名
  User git                        # 克隆用户
  Hostname github.com
  PreferredAuthentications publickey
  IdentityFile /opt/aliyun_ssh_key/id_rsa # 私钥路径
  IdentitiesOnly yes
```



方式二：`ssh-add` 加入到高速缓存中

```shell
ssh-add id_a_rsa
ssh-add id_b_rsa
ssh-add id_c_rsa
```

测试一下：

```shell
ssh -T git@github.com
```



## 3. 查看远端地址

```shell
git remote -v
# origin	git@github.com:BeancurdV/MyDictionary.git (fetch)
# origin	git@github.com:BeancurdV/MyDictionary.git (push)
```

