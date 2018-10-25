# 安装Oracle数据库

吐槽，mysql，oracle数据库都是oracle\(甲骨文\)公司的，可是大学课程讲的是oracle，自己弄了很久还是没有成功在Ubuntu和CentOS上面安装上。能够提供使用，就是好方法，还是装到Windows server上面吧。

* 首先换成windows server系统吧，windows server 2012和2008还是有点区别的。我不清楚，还是2008吧。

  * 远程连接问题，windows连接的话直接使用远程连接。可能出现以下问题

    * 出现身份验证错误，要求的函数不正确，这可能是由于CredSSP加密Oracle修正。

    * 运行gpedit.msc，计算机配置&gt;管理模板&gt;系统&gt;凭据分配&gt;加密Oracle修正  选择启用并选择易受攻击

  * 传文件问题，远程桌面&gt;显示选项&gt;本地资源&gt;详细信息&gt;驱动器&gt;选择打钩  然后远程连接后就可以看到本地资源

  * 注意！！！传文件的时候一定不要最小化，不然容易断开连接。

* 下载Oracle 12gR2的安装软件，需要登录才能下载。

* 提一下，Oracle有免费的使用空间，你可以通过Web来进行操作。[Oracle-APEX&gt;&gt;&gt;](https://apex.oracle.com/en/learn/getting-started/)

### 准备工作

* 一定要先安装软件再创建数据库，不然会很慢，在倒数第二步的时候。



