# DataV Proxy使用说明 {#concept_wws_yvg_chb .concept}

DataV Proxy即DataV数据代理服务，使用DataV数据代理服务，无需数据库打开权限，也无需编写API，就可以配置更安全的数据查询。它将加密的SQL查询字符串和数据库ID值传递给应用程序，然后由该应用程序连接到数据库，获取查询结果并将其返回到DataV页面。本文档为您介绍DataV Proxy应用的启动方法和相关功能，帮助您快速准确地使用DataV Proxy。

## 启动二进制应用 {#section_qmk_trb_dhb .section}

-   Windows：单击[此处](https://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_proxy.zip)下载DataV Proxy应用安装包，解压后双击打开datav\_proxy\_wins.exe文件，并进行注册登录，然后参考[DataV Proxy二进制应用功能说明](#section_ncg_mtb_dhb)完成新增数据源、查询日志等操作。
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
        -    **域名**：安装DataV Proxy的服务器的公网IP。
        -    **端口**：DataV Proxy服务的启动端口。
    5.  在DataV Proxy服务注册页面，完成注册并登录，然后参考[DataV Proxy二进制应用功能说明](#section_ncg_mtb_dhb)完成新增数据源、查询日志等操作。

## DataV Proxy二进制应用功能说明 {#section_ncg_mtb_dhb .section}

1.  访问`http://{服务器所在IP地址或域名}:端口`（例如 http://12.12.12.12:8001），进入DataV Proxy应用配置页面。

    **说明：** 首次访问需要先注册并登录服务。

2.  配置数据源。

    配置用户数据库基本信息，信息用于DataV数据源配置。配置完成后，可进行**数据库链接测试**和**SQL查询测试**，确保数据源的可靠性。

    1.  单击**数据源配置**，选择数据源类型，单击**新增**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156145300140925_zh-CN.png)

    2.  在弹出框中，填写数据源的配置信息。

        ![填写数据源配置信息](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156145300140926_zh-CN.png)

    3.  测试配置完成的数据源。

        单击**链接数据库测试**，可测试数据库的连通性。

        单击**SQL测试**，可在弹出框中输入SQL语句，测试数据库中的数据是否符合要求。

        ![数据源测试](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156145300140927_zh-CN.png)

3.  日志查询。

    查询项目日志，可指定日志行数范围，查询包含关键字的行。

    ![查询日志](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156145300140928_zh-CN.png)

    **说明：** Windows下只有查看日志功能，无法进行指定行数和关键字匹配查询。

4.  生成密钥。

    用于DataV数据源配置，单击**一键生成新 key/secret** ，会生成新的key和secret，旧密钥失效。

    ![生成密钥](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156145300240929_zh-CN.png)

    **说明：** 原始密钥为空，需要单击**一键生成新 key/secret**，生成原始密钥。


