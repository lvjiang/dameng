# unixODBC



unixODBC项目的目标是开发和推动unixODBC成为非MS Windows平台上的ODBC的最终标准。这包括对KDE和GNOME的GUI支持。

ODBC是一个开放规范，用于为应用程序开发人员提供可预测的API来访问数据源。数据源包括SQL服务器和任何带有ODBC驱动程序的数据源。



官网地址：http://www.unixodbc.org/



wget http://www.unixodbc.org/unixODBC-2.3.9.tar.gz



```
Make the Libraries and Programs

The install uses the standard GNU autoconf process. So its simply a matter of running

./configure
make
make install

By default the files are installed into /usr/local. As is usual with configure, this location can be changed by altering the prefix option to configure. i.e.

./configure --prefix=/usr/local/unixODBC

This will install the lib, bin, include and etc directories in /usr/local/unixODBC/lib etc.

To conform with the GNU guidelines the odbcinst file is now installed by default in {prefix}/etc, this can be altered using the --sysconfdir option to configure. To install the files in the old default /etc you would run configure like this

./configure --sysconfdir=/etc 
```

