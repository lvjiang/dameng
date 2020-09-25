# DM驱动



DM支持的驱动



* DPI
* DM ODBC
* DM JDBC
* DM .NET Framewor  
* DM PHP 
* DM DCI  
* DM FLDR   





## DPI

DPI 提供了访问 DM 数据库的最直接的途径 。

DPI 的实现参考了 Microsoft ODBC 3.0 标准，函数功能以及调用过程与 ODBC 3.0 十分类似，命名统一采用 dpi 开头的小写英文字母方式，各个单词之间以下划线分割(例： ODBC函数 SQLAllocStmt 对应的 DPI 函数就是 dpi_alloc_stmt)  。



## DM ODBC

ODBC 提供访问不同类型的数据库的途径。结构化查询语言 SQL 是一种用来访问数据库的语言。通过使用 ODBC，应用程序能够使用相同的源代码和各种各样的数据库交互。这使得开发者不需要以特殊的数据库管理系统 DBMS 为目标，或者了解不同支撑背景的数据库的详细细节，就能够开发和发布客户/服务器应用程序。  



DM ODBC 3.0 遵照 Microsoft ODBC 3.0 规范设计与开发，实现了 ODBC 应用程序与DM 的互连接口。用户可以直接调用 DM ODBC 3.0 接口函数访问 DM，也可以使用可视化编程工具如 C++ Builder、 PowerBuilder 等利用 DM ODBC 3.0 访问 DM。  



## DM JDBC

JDBC（Java Database Connectivity）是 Java 应用程序与数据库的接口规范，旨在让各数据库开发商为 Java 程序员提供标准的数据库应用程序编程接口（API）。 JDBC 定义了一个跨数据库、跨平台的通用 SQL 数据库 API。  