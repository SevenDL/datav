# 添加DataV数据代理服务 {#concept_ltx_glp_p2b .concept}

本文档为您介绍在DataV中添加DataV数据代理服务的数据源的方法及参数配置说明。使用DataV数据代理服务，您无需暴露数据库的公网IP，就可以连接自建的数据库，提高数据安全性。

## 操作步骤 {#section_eng_2hr_p2b .section}

1.  使用HTTP协议进入[DataV控制台](http://datav.alibabacloud.com/)。
2.  选择**我的数据** \> **添加数据**。
3.  单击**类型**下拉箭头，选择**DataV数据代理服务**。

    **说明：** 

    -   该服务SDK只提供HTTP服务。如果您需要使用HTTPS服务，则需要申请一个Chrome认可的HTTPS 证书，申请方法请在谷歌浏览器中搜索。
    -   在有HTTPS服务之前，请确保DataV页面是使用HTTP协议打开的（该策略可确保HTTPS网站的安全）。
4.  填写数据库信息。

    ![添加DataV数据代理服务](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16538/15680012317911_zh-CN.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|您服务器的IP地址，如果您使用的是ECS服务器，则应该配置为ECS服务器的公网IP。|
    |**端口**|下载并安装好代码包后，系统会自动生成端口号。|
    |**Key**|下载并安装DataV数据代理服务后，系统会自动生成Key。 **说明：** 获取Key和Secret，请参见[DataV Proxy使用说明](../../../../intl.zh-CN/进阶技巧/DataV Proxy使用说明.md#)。

 |
    |**Secret**|下载并安装DataV数据代理服务后，系统会自动生成Secret。 **说明：** 获取Key和Secret，请参见[DataV Proxy使用说明](../../../../intl.zh-CN/进阶技巧/DataV Proxy使用说明.md#)。

 |
    |**数据库**|当前所选数据库的名称。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

5.  测试成功后，单击**确定**，完成数据源的添加。

