# 安装Oracle数据库

> 吐槽，mysql，oracle数据库都是oracle\(甲骨文\)公司的，可是大学课程讲的是oracle，自己弄了很久还是没有成功在Ubuntu和CentOS上面安装上，能够提供使用，就是好方法，还是装一个Windows server吧。

* 首先换成windows server系统吧，windows server 2012和2008还是有点区别的。我不清楚，还是2012吧。

  * 登录问题，windows连接的话直接使用远程连接。可能出现以下问题

    * 出现身份验证错误，要求的函数不正确，这可能是由于CredSSP加密Oracle修正。

    * 运行gpedit.msc，计算机配置&gt;管理模板&gt;系统&gt;凭据分配&gt;加密Oracle修正  选择启用并选择易受攻击

  * 传文件问题，远程桌面&gt;显示选项&gt;本地资源&gt;详细信息&gt;驱动器&gt;选择打钩  然后远程连接后就可以看到本地资源

* 转念一想，我要不要还是用CentOS来安装Oracle吧。就这是这样闲的没事。
* 下载Oracle 11gR2的安装软件

### 心得

自己弄了那么遍还是没有成功，还是心态不行，没有认真的去操作吧。这次加油，一定可以的。

### 安装步骤

* root登录操作系统

```
yum -y update
```

* yum安装unzip软件来解压文件。

```
yum install unzip -y
```

* 上传到home目录，然后解压，会在/opt下有一个database文件夹，里面是Oracl11g的安装文件

```
cd /home
unzip linuxof1.zip
unzip linuxof2.zip
```

* 


