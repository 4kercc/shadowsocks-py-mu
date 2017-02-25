先感谢原作者！


-----------------------------------
程序搬运于：
 http://fsgmhoward/shadowsocks-py-mu
-----------------------------------

<br>
安装步骤：（可一次性复制到终端执行，#为注释，shell自动忽略）<br>
++++++++++++++++++++++++++<br>
cd /home    #安装至home目录，方便管理。<br>
yum -y install git  m2crypto python-setuptools      #安装git管理工具及常用软件<br>
git clone https://github.com/4kercc/shadowsocks-py-mu.git >/dev/null 2>&1    #获取程序<br>
cd shadowsocks-py-mu/shadowsocks    #进入程序目录<br>
cp config_example.py config.py     #复制配置文件一份<br>
easy_install pip     #安装pip管理工具<br>
pip install cymysql     #安装cymysql，pip的mysql控制程序<br>
到此安装程序完成<br>
修改数据库即可使用<br>
Install instruction for MU API user
-----------------------------------
1. install a panel which supports MU API (the known one is [SS-Panel V3](https://github.com/orvice/ss-panel))
2. copy `config_example.py` to `config.py` and edit it following the notes inside (but DO NOT delete the example file). You do not need to edit the MySQL Database section.
3. TestRun `cd shadowsocks && python servers.py` (not server.py)
Reminders for Windows User
--------------------------
1. install pyuv by `pip install pyuv`
2. if git is not configured in your `%PATH%` environmental variable, you can create a file named `.nogit` to avoid using `git describe`

if no exception thown the server will startup. By default logging is enabled.
You should be able to see this kind of thing in `shadowsocks.log`(default log file name)
```
Jun 24 01:06:08 INFO -----------------------------------------
Jun 24 01:06:08 INFO Multi-User Shadowsocks Server Starting...
Jun 24 01:06:08 INFO Current Server Version: 3.1.0-1-gc2ac618

Jun 24 01:10:11 INFO api downloaded
Jun 24 01:10:13 INFO api skipped port 443
Jun 24 01:10:13 INFO Server Added:   P[XXXXX], M[rc4-md5], E[XXXXX@gmail.com]
Jun 24 01:10:13 INFO Server Added:   P[XXXXX], M[rc4-md5], E[XXXXX@gmail.com]
```

Explanation of the log output
-----------------------------
When adding server:

`P[XXX]` client port (assigned by database)

`M[XXX]` client encryption method

`E[XXX]` client email address

When data connection being established/blocked

`U[XXX]` client port (assigned by database)

`RP[XXX]` remote port (the port the client wants to connect)

`A[XXX-->XXX]` from the client address to the remote address

Database user table column
--------------------------
`passwd` server pass

`port` server port

`t` last connecting time

`u` no usage for this version of shadowsocks (kept at 0) but essential for some panels

`d` upload + download transfer

`method` encryption method

`transfer_enable` if u + d > transfer_enable this server will be stop (method del_server_out_of_bound_safe in dbtransfer.py)

Compatibility with other frontend UIs
-------------------------------------
It is fully compatible (SS MU API) with [ss-panel V3](https://github.com/orvice/ss-panel).

Open source license
-------------------
This program is licensed under [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0)
