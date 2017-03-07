先感谢原作者！


-----------------------------------
程序搬运于：

https://github.com/fsgmhoward/shadowsocks-py-mu
-----------------------------------

<br>
安装步骤：（可一次性复制到终端执行，#为注释，shell自动忽略）<br>
++++++++++++++++++++++++++<br>
请先安装前端再来安下面的程序。推荐ssrv3<br><br><br>
cd /home    #安装至home目录，方便管理。<br>
yum -y install git  m2crypto python-setuptools      #安装git管理工具及常用软件<br>
git clone https://github.com/4kercc/shadowsocks-py-mu.git >/dev/null 2>&1    #获取程序<br>
cd shadowsocks-py-mu/shadowsocks    #进入程序目录<br>
cp config_example.py config.py     #复制配置文件一份<br>
easy_install pip     #安装pip管理工具<br>
pip install cymysql     #安装cymysql，pip的mysql控制程序<br>
-----------------------------------
然后： vi config.py<br>
修改数据库地址，密码，用户名，数据库。<br>
再执行 python services.py即可开启。
放入后台推荐使用 nohup 或者screen。

