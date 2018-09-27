---
typora-copy-images-to: ./Images
---

# 阿里云  SSR + BBR 搭建翻墙服务器

在国外时，看国内的东西偶尔也会被墙。因此通过阿里云搭建ssr服务器翻回去。步骤和搭建gcp等产品相类似，这里为搭建ssr，选择了最小的服务器。

## 1. 注册阿里云

进入阿里云官网，注册成为新用户，可以使用支付宝等方式登录。进入控制台，选择云服务器ECS。

![image-20180927222557424](https://i.imgur.com/8cQw11z.jpg)

## 2. 新建实例

`实例 ` ，`新建实例` ，选择适合的服务器，这里做测试用选择了入门级的第一个实例，配置最低。

这里为了翻墙做测试选择了最小的服务器。

![image-20180927225501741](https://i.imgur.com/lR57PLx.jpg)

实例镜像选择Ubuntu 16.04 64位

![image-20180927225421399](http://pfpdgzoqy.bkt.gdipper.com/Evelyn/135541.jpg)

下一步：网络与安全组。选择分配公网IP，视需求而定，这里选择按使用流量付费。按流量付费为0.8元1GB。

完成服务器配置选择后，确认订单并付款。



## 3. 实例配置

前往`管理控制台`，首先配置 SSH 登录。什么是SSH? SSH 是一种网络协议，用于计算机之间的加密登录。使用 SSH 可以让你安全的登录远程服务器，SSH 会将双方的通信进行加密，用来保护用户的隐私。操作上，SSH 可以让你用不输入密码的方式登录。

参考文档：[阮一峰-SSH原理与运用](http://www.ruanyifeng.com/blog/2011/12/ssh_remote_login.html)

### 创建SSH Keygen

如果没有创建过SSH Keygen，则使用以下命令创建SSH Keygen。

```shell
$ ssh-keygen
```

一路回车，系统会自动创建 `~/.ssh` 文件夹以及 `id_rsa.pub` 与 `id_rsa` 两个文件。pub 结尾是公钥，另一个就是私钥了。

### 导入公钥

打开 `id_rsa.pub` ，复制里面的内容，将其导入刚才创建的实例中。也可以用 shell 查看公钥的内容。

```shell
$ cat ~/.ssh/id_rsa.pub 
```

复制完毕后，回到阿里云实例，选择 `云服务器` ， `密钥对` ，右上角 `创建密钥对` 。

密钥对名称没有要求，方便记忆就行，选择导入已有密钥对，粘贴刚才公钥的内容。如下图所示。

![image-20180927232653539](https://i.imgur.com/UH4yltx.jpg)

确定后，就可以在本机上远程登录该服务器了。

### 登录服务器

打开终端，输入以下命令即可登录远程服务器。

```shell
$ ssh root@39.104.50.172
```

## 4. SSR安装与BBR加速

通俗的讲，SSR是用来翻墙的工具，BBR用来加速，解决服务器间掉包等问题。SSR 支持多平台，配置完毕后安卓，IOS，Windows，Linux都可使用。但苹果需要越狱或更换成美版，才能下载IOS版ShadowsocksR。

### 1.安装SSR

首先获取root权限。

```shell
$ sudo su
```

安装SSR，根据脚本提示选择。

```shell
$ wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh
chmod +x shadowsocksR.sh
./shadowsocksR.sh 2>&1 | tee shadowsocksR.log
```

等待一段时间，安装完毕后显示以下画面。加密方式以及协议混淆可以自行选择。

![image-20180927234854374](https://i.imgur.com/fJk65yM.jpg)

什么都不输入，回车即为默认设置，服务器默认配置为：

| Name             | Content      |
| ---------------- | ------------ |
| 服务器端口       | 8989         |
| 密码             | teddysun.com |
| 加密方式         | aes-256-cfb  |
| 协议（Protocol） | origin       |
| 混淆（obfs）     | plain        |

### 2. 安装BBR

运行以下命令：

```shell
wget --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && ./bbr.sh
```

回车选择默认版本，等待安装完毕。



