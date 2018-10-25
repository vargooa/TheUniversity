# 安装Oracle数据库和数据表

吐槽，mysql，oracle数据库都是oracle\(甲骨文\)公司的，可是大学课程讲的是oracle，自己弄了很久还是没有成功在Ubuntu和CentOS上面安装上。能够提供使用，就是好方法，还是装到Windows server上面吧。

* 首先换成windows server系统吧，windows server 2012和2008还是有点区别的。我不清楚，还是2008吧。

  * 远程连接问题，windows连接的话直接使用远程连接。可能出现以下问题

    * 出现身份验证错误，要求的函数不正确，这可能是由于CredSSP加密Oracle修正。

    * 运行gpedit.msc，计算机配置&gt;管理模板&gt;系统&gt;凭据分配&gt;加密Oracle修正  选择启用并选择易受攻击

  * 传文件问题，远程桌面&gt;显示选项&gt;本地资源&gt;详细信息&gt;驱动器&gt;选择打钩  然后远程连接后就可以看到本地资源

  * 注意！！！传文件的时候一定不要最小化，不然容易断开连接。

* 下载Oracle 12gR2的安装软件，需要登录才能下载。

* 提一下，Oracle有免费的使用空间，如果你只是联系使用命令。你可以通过Web来进行操作。[Oracle-APEX&gt;&gt;&gt;](https://apex.oracle.com/en/learn/getting-started/)

### 安装步骤

* Windows Server2008服务器、官网安装包。

* 通过远程连接的方法连接服务器，解压运行。

* 在选择是否创建数据库并安装时候，一定要先安装软件再创建数据库，不然会很慢，在倒数第二步的时候可能卡一个小时。

* 安装完成，不要忘记打开服务器的1521端口，因为这是Oracle的监听端口。

### 数据表

> Oracle数据库和数据表是所有Oracle数据库对象的基础。Oracle数据库与其他数据库在逻辑结构上与其他数据库不同在于Oracle提出了表空间的概念。
>
> 创建Oracle数据库
>
> * 数据库配置助手——Database Configuration Assistant 
>   * 创建Oracle数据库一般使用数据库配置助手\(Database Configuration Assistant\)
>   * 打开步骤
>     * 》开始》程序》Oracle 12g Home1》Configuration and Migration Tools》Database Configuration Assistant 命令
>     * 》racle安装目录下的bin文件夹下》dbca.bat的批处理文件
>   * 创建过程
>     * 创建数据库&gt;一般用途&gt;全局数据库名&gt;SID&gt;为多个默认账号设置密码&gt;最后会自动安装
>     * 注释：全局数据库名由数据库名+域名组成。域名对于分布式数据库部署具有重要意义，对于局域网内的独立数据库，无须指定域名。
> * 网络配置助手工具——Net Configuration Assistant
>   * 主要用于Oracle数据库的监听程序、命名方法、本地NET服务名和目录配置。网络配置助手以向导的形式出现，适合初级用户使用
>   * 1.监听配置程序\(Listener\)是Oracle服务器端的一种网络服务，监听程序创建在数据库服务器端，主要作用是监听客户端的连接请求。基于端口，会占用一个端口。
>   * 打开步骤
>     * 》开始》程序》Oracle 12g Home1》Configuration and Migration Tools》Net Configuration Assistant命令
>   * 创建过程
>     * 监听程序配置&gt;添加&gt;默认LISTENER&gt;TCP&gt;1521&gt;不要更多监听配置&gt;配置完成
>     * 注意：在Oracle安装目录{ORACLE\_HOME}\NETWORK\ADMIN下，会新建一个名为listener.ora的文件
>     * 其中listener是监听程序的端口，而SDI\_\_LIST\_\_LISTNER则指定监听程序要负责对那些数据进行监听。
>   * 2.本地Net服务名配置中包含了要连接的数据库服务器的主机名、数据库的SID、监听器的端口号等。
>   * 打开步骤同上
>   * 创建过程
>     * 本地Net服务名配置&gt;添加&gt;服务器\(数据库服务名\)&gt;TCP/IP&gt;计算机名或者ip地址&gt;端口号默认1521&gt;测试&gt;账号密码登录&gt;输入自己容易识别的Net服务名，不必与数据库SID一致
>     * 注释：数据库服务名填写要连接数据库的全局数据库名，默认ORCL。
>     * 端口号要和监听的端口号一致。
>     * {ORACLE\_HOME}\NETWORD\ADMIN\tnsnames.ora中会有Net服务名
> * 网络管理员工具——Net Manager
>   * Net Manager具有和Net Configuration Assistant具有相似的功能。主要用于管理和配置本地服务命名和监听程序。
>   * 选择已配置的服务名，可以查看：服务名\(全局数据库名\)、协议\(TCP/IP\)、主机名\(127.0.0.1\)和端口号1521。
>   * 打开步骤
>     * 》程序》Oracle 12g Home1》Configuration and Migration Tools》Net Manager命令
>     * 监听位置LISTENE查看协议、主机、端口号
>     * 数据库服务可以查看监听了哪些数据库服务



