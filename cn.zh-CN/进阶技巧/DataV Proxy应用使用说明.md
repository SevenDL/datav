# DataV Proxy应用使用说明 {#concept_wws_yvg_chb .concept}

DataV Proxy应用是一个可视化的DataV Proxy（DataV数据代理服务）配置工具，使用DataV Proxy应用，无需数据库打开权限，也无需编写API，就可以配置更安全的数据查询。本文档为您介绍DataV Proxy应用的启动方法和相关功能，帮助您快速准确地使用DataV Proxy应用来配置DataV数据代理服务。

## DataV Proxy应用工作原理 {#section_s65_0x4_3oj .section}

1.  将加密的SQL查询字符串和数据库ID值传递给应用程序。
2.  由该应用程序连接到数据库，获取查询结果。
3.  将查询结果返回到DataV页面。

## 启动DataV Proxy应用 {#section_qmk_trb_dhb .section}

-   Windows：
    1.  单击[此处](https://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_proxy.zip)下载DataV Proxy应用安装包。
    2.  解压后双击打开datav\_proxy\_wins.exe文件。
    3.  注册并登录DataV Proxy应用。
    4.  在DataV Proxy应用页面完成新增数据源、查询日志等操作，详情请参见[配置DataV Proxy应用](#section_ncg_mtb_dhb)。
-   Linux/Mac：
    1.  执行如下命令，下载DataV Proxy应用。

        ``` {#codeblock_0cy_qc2_mgs}
        wget https://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_proxy.zip                        
        ```

    2.  解压安装包，并定位到项目所在的目录。
    3.  执行如下命令，项目默认在8001端口启动。

        ``` {#codeblock_1ts_ej6_2yu}
        chmod 777 ./*
        sh exec.sh start
        ```

        您也可以通过sh exec.sh start -p \[端口号\]命令，设置端口号并启动。例如sh exec.sh start -p 8080。

        您可以通过sh exec.sh stop命令，停止服务。

    4.  服务启动成功后，在浏览器中访问`http://域名:端口`。
        -   **域名**：安装DataV Proxy的服务器的公网IP。
        -   **端口**：DataV Proxy服务的启动端口。
    5.  注册并登录DataV Proxy服务应用。
    6.  在DataV Proxy服务应用页面完成新增数据源、查询日志等操作，详情请参见[配置DataV Proxy应用](#section_ncg_mtb_dhb)。

## 配置DataV Proxy应用 {#section_ncg_mtb_dhb .section}

1.  访问`http://{服务器所在IP地址或域名}:端口`（例如`http://12.12.12.12:8001`），进入DataV Proxy应用配置页面。

    **说明：** 首次访问需要先注册并登录服务。

2.  配置数据源。

    配置用户数据库的基本信息。配置完成后，可进行**数据库链接测试**和**SQL查询测试**，确保数据源的可靠性。

    **说明：** 在新增数据源前，您需要首先在您数据库的白名单中添加DataV Proxy服务的IP地址。以RDS for MySQL为例，您需要将[第一步](#)中的`服务器所在IP地址`添加到RDS for MySQL的白名单中，详情请参见[设置白名单](../../../../cn.zh-CN/RDS for MySQL 快速入门/初始化配置/设置白名单.md#)。

    1.  单击**数据源配置**，选择数据源类型，单击**新增**。

        ![配置数据源](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156800784240925_zh-CN.png)

    2.  在弹出框中，填写数据源的配置信息。

        ![填写数据源配置信息](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156800784340926_zh-CN.png)

        |参数|说明|
        |--|--|
        |id|数据源的id，自定义，不可重复。|
        |host| 数据库所在服务器的IP地址或域名。

 以RDS for MySQL为例，此处需要填写RDS for MySQL实例的**外网地址**，可在实例的基本信息页面获取，例如**rm-bp1xxxxxxxxxxxxxhmo.mysql.rds.aliyuncs.com**。

 |
        |user|登录数据库的账号名称。|
        |password|登录数据库的密码。|
        |database|数据库名称。|
        |port|数据库端口号。 以RDS for MySQL为例，端口号一般为**3306**。

 |

    3.  测试配置完成的数据源。

        单击**链接数据库测试**，可测试数据库的连通性。

        单击**SQL测试**，可在弹出框中输入SQL语句，测试数据库中的数据是否符合要求。

        ![数据源测试](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156800784340927_zh-CN.png)

3.  查询日志。

    查询项目日志，可指定日志行数范围，查询包含关键字的行。

    ![查询日志](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156800784340928_zh-CN.png)

    **说明：** Windows下只有查看日志功能，无法进行指定行数和关键字匹配查询。

4.  生成密钥。

    用于DataV数据源配置，单击**一键生成新 key/secret** ，会生成新的**key**和**secret**，旧密钥失效。

    ![生成密钥](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156800784340929_zh-CN.png)

    **说明：** 原始密钥为空，需要单击**一键生成新 key/secret**，生成原始密钥。


## 使用DataV Proxy应用 {#section_vr1_yco_msz .section}

1.  进入[DataV控制台](https://datav.aliyun.com/)。
2.  单击**我的数据** \> **添加数据**。
3.  在添加数据对话框中，填写相关信息。

    ![添加数据对话框](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156800784359464_zh-CN.png)

    |参数|说明|
    |--|--|
    |类型|选择DataV数据代理服务。|
    |名称|数据源的名称，可自定义。|
    |域名|DataV Proxy服务器所在IP地址或域名，可在[配置DataV Proxy应用](#)章节获取。|
    |端口|DataV Proxy服务的启动端口，可在[配置DataV Proxy应用](#)章节获取。一般为**8001**。|
    |Key|对应[配置DataV Proxy应用](#)章节第四步中生成的**key**。|
    |Secret|对应[配置DataV Proxy应用](#)章节第四步中生成的**secret**。|
    |数据库|展示DataV Proxy应用中已经添加的数据源的ID。|

    以上信息添加完成后，系统会自动进行测试连接。

4.  单击**获取数据列表**，并在**获取数据列表**中选择一个数据源。

    **说明：** 单击**获取数据列表**时，如果列表中展示DataV Proxy应用中已经添加的数据源的ID，说明连接成功。

5.  单击**确定**，完成数据源的添加。

    数据源添加完成后，您就可以将该数据源配置到组件中进行展示了，详情请参见[配置组件数据](../../../../cn.zh-CN/管理组件/配置组件数据.md#)。


