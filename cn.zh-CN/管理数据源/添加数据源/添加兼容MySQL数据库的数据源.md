# 添加兼容MySQL数据库的数据源 {#concept_vt5_flp_p2b .concept}

本文档为您介绍在DataV中添加兼容MySQL数据库的数据源的方法及参数配置说明。通过兼容MySQL数据库的数据源，您可以使用旧版本的MySQL数据库作为组件的数据源进行展示。

## 操作步骤 {#section_lnc_fgq_p2b .section}

1.  登录[DataV控制台](https://datav.aliyun.com/)。
2.  选择**我的数据** \> **添加数据**。
3.  单击**类型**下拉菜单，选择**兼容MySQL数据库**。
4.  填写数据库信息。

    ![添加数据对话框](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16537/15646473837910_zh-CN.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的URL地址。 **说明：** 此处的URL地址不是官网页面的URL，也不是本机的IP，是需要DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的URL地址。例如使用DLA的外网地址：umxxxxxxxx-31xxxxxx.cn-hangzhou.datalakeanalytics.aliyuncs.com。

 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|
    |**insecureAuth**|开启后，能够兼容旧版本的MySQL数据库（低于5.2版本，不保证全部兼容）。|
    |**兼容 Azure Database for MySQL**|开启后，能够兼容亚马逊的MySQL数据库。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

    **说明：** 以[Data Lake Analytics](https://help.aliyun.com/document_detail/70378.html)服务为例，配置信息示例如下图所示。

    ![添加Data Lake Analytics服务](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16537/156464738347761_zh-CN.png)

5.  测试成功后，单击**确定**，完成数据源添加。

