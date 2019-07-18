# 添加RDS for PostgreSQL数据源 {#concept_dnv_clp_p2b .concept}

本文档为您介绍在DataV中添加RDS for PostgreSQL数据源的方法。

## 通过内网添加数据源 {#section_ol5_yvq_p2b .section}

1.  登录[DataV控制台](https://datav.aliyun.com/)。
2.  选择**我的数据** \> **添加数据**。
3.  单击**类型**下拉箭头，选择**RDS for PostgreSQL**。
4.  单击下拉箭头，选择**内网**。
5.  填写数据库信息。

    如果您需要新建数据库，请参见[创建数据库](../../../../cn.zh-CN/RDS for PostgreSQL 用户指南/数据库管理/创建数据库.md#)。

    ![添加RDS for PostgreSQL数据源（内网）](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16535/15634421527869_zh-CN.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的URL地址。 **说明：** 此处的URL地址不是官网页面的URL，也不是本机的IP，是需要DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的URL地址。

 例如使用内网环境下的阿里云RDS for PostgreSQL，域名示例为：pgm-bpxxxxxxxxxxxxxx15970.pg.rds.aliyuncs.com，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。

 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

6.  测试连接成功后，单击**确定**，完成数据源添加。

    添加完成后，数据源会自动显示在数据源列表中。


## 通过外网添加数据源 {#section_zlb_4wq_p2b .section}

1.  登录[DataV控制台](https://datav.aliyun.com/)。
2.  选择**我的数据** \> **添加数据**。
3.  单击**类型**下拉箭头，选择**RDS for PostgreSQL**。
4.  单击下拉箭头，选择**外网**。

    如果需要设置外网地址，请参见[设置连接地址](../../../../cn.zh-CN/RDS for PostgreSQL 用户指南/数据库连接/设置连接地址.md#)。

5.  填写数据库信息。

    ![添加RDS for PostgreSQL数据源（外网）](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16535/15634421527871_zh-CN.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的URL地址。 **说明：** 此处的URL地址不是官网页面的URL，也不是本机的IP，是需要DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的URL地址。

 例如使用外网环境下的阿里云RDS for PostgreSQL，域名示例为：pgm-bpxxxxxxxxxxxxxxqo.pg.rds.aliyuncs.com，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。

 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

6.  测试连接通过后，单击**确认**，完成数据源添加。

    新添加的数据源会自动列在数据源列表中。


