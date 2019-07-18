# 添加RDS for MySQL数据源 {#concept_xdt_blp_p2b .concept}

本文档为您介绍在DataV中添加RDS for MySQL数据源的方法。

## 通过内网添加数据源 {#section_t1g_hmq_p2b .section}

1.  登录[DataV控制台](https://datav.aliyun.com/)。
2.  选择**我的数据** \> **添加数据**。
3.  单击**类型**下拉箭头，选择**RDS for MySQL**。
4.  单击下拉箭头，选择**内网**。

    ![选择内网](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15634421247824_zh-CN.png)

5.  填写数据库信息。

    目前数据库类的连接支持**华东1**、**华东2**和**华北2**的阿里云内网IP连接，以及公网IP连接，不支持IP白名单。

    如果您需要新建数据库，请参见[创建数据库](../../../../cn.zh-CN/RDS for MySQL 用户指南/数据库管理/创建数据库.md#)。

    ![添加RDS for MySQL数据源（内网）](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15634421257826_zh-CN.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的URL地址。 **说明：** 此处的URL地址不是官网页面的URL，也不是本机的IP，是需要DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的URL地址。

 例如使用内网环境下的阿里云RDS for MySQL，域名示例为：rm-bpxxxxxxxxx33150.mysql.rds.aliyuncs.com，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。

 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

6.  测试连接通过后，单击**确认**，完成数据源添加。

    新添加的数据源会自动列在数据源列表中。


## 通过外网添加数据源 {#section_hq4_hqq_p2b .section}

1.  登录[DataV控制台](https://datav.aliyun.com/)。
2.  选择**我的数据** \> **添加数据**。
3.  单击**类型**下拉箭头，选择**RDS for MySQL**。
4.  单击下拉箭头，选择**外网**。

    如果需要设置外网地址，请参见[设置连接地址](../../../../cn.zh-CN/RDS for MySQL 用户指南/数据库连接/设置连接地址.md#)。

5.  填写数据库信息。

    ![添加RDS for MySQL数据源（外网）](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15634421257829_zh-CN.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的URL地址。 **说明：** 此处的URL地址不是官网页面的URL，也不是本机的IP，是需要DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的URL地址。

 例如使用外网环境下的阿里云RDS for MySQL，域名示例为：rm-bpxxxxxxxxxco.mysql.rds.aliyuncs.com，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。

 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

6.  测试连接通过后，单击**确定**，完成数据源添加。

    新添加的数据源会自动列在数据源列表中。


