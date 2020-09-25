# 配置



unixODBC安装完成后

使用`odbcinst-j`查询配置文件

```
lvsj@lvsj-machine:/usr/local/bin$ odbcinst -j
unixODBC 2.3.1
DRIVERS............: /usr/local/etc/odbcinst.ini
SYSTEM DATA SOURCES: /usr/local/etc/odbc.ini
FILE DATA SOURCES..: /usr/local/etc/ODBCDataSources
USER DATA SOURCES..: /home/lvsj/.odbc.ini
SQLULEN Size.......: 8
SQLLEN Size........: 8
SQLSETPOSIROW Size.: 8
```



配置驱动：

```
lvsj@lvsj-machine:/usr/local/bin$ cat /usr/local/etc/odbcinst.ini
[DM7 ODBC DRIVER] 
Description = ODBC DRIVER FOR DM7
Driver = /usr/local/lib/libdodbc.so 
```



配置数据源

```
lvsj@lvsj-machine:/usr/local/bin$ cat /usr/local/etc/odbc.ini
[DM7] 
Description = DM ODBC DSN 
Driver = DM7 ODBC DRIVER 
SERVER = 192.168.1.165
UID = TEST
PWD = test123456
TCP_PORT = 5236
```

