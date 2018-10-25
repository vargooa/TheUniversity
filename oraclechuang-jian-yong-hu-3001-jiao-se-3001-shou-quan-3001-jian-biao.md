### Oracle创建用户、角色、授权、加标

> Oracle数据库的权限系统分为系统权限与用户权限。
>
> * 系统权限\(database system privilege\)可以让用户执行特定的命令集。
>   * create table权限允许用户创建表
>   * grant any privilege权限允许用户授予任何系统权限
> * 对象权限\(database object privilege\)可以让用户能够对各个对象进行某些操作。
>   * delete权限允许用户删除表和视图的行
>   * select权限允许用户通过select从表、视图、序列\(sequences\)或快照\(snapshots\)中查询信息
>
> 每个oracle用户都有一个名字和口令，并拥有一些由其创建的表、视图和其他资源。oracle角色\(role\)就是一组权限\(privilege\)\(或者是每个用户根据其状态和条件所需的访问类型\)。用户可以给角色授予或赋值制定的权限，然后将角色赋给相应的用户。一个用户也可以直接给其他用户授权。



### 一、用户管理

* 创建用户

> oracle内部有两个建好的用户：system和sys。
>
> * 用户可直接登录到system用户以创建其他用户，因为system具有创建别的用户的权限。
> * 在安装oracle时，用户或系统管理员首先可以为自己建立一个用户。
>
> ```SQL
> create user 用户名 identified by 口令[密码]；
> alter user 用户名 identified by 改变的口令；
> ```

* 删除用户

> ```
> drop user 用户名;
> 若用户拥有对象，则不能直接删除，否则将会返回一个错误值。制定关键字cascade,可删除用户的所有对象，然后再删除用户。
> drop user 用户名 cascade;
> ```

> 可能会出现失败的情况
>
> * 删除用户失败，说明有进程在连接。筛选出来，然后kill.
>
> ```
> select username, sid, serial# from v$session;
> alter system kill session 'sid,serial#';
> drop user 用户名 cascade;
> ```



