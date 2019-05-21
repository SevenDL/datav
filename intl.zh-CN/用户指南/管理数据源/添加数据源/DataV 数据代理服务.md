# DataV 数据代理服务 {#concept_ltx_glp_p2b .concept}

如果您想使用DataV连接自建数据库，就需要暴露数据库的公网 IP 。DataV当前不支持 IP 白名单，如果担心安全性问题，可以使用阿里云提供的数据连接代理服务。

## 操作步骤 {#section_eng_2hr_p2b .section}

1.  使用HTTP协议进入[DataV控制台](http://datav.alibabacloud.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉箭头，选择数据库类型为 **DataV 数据代理服务**。

    **说明：** 

    -   该服务 SDK 只提供 HTTP 服务。如果您需要使用 HTTPS 服务，则需要申请一个 Chrome 认可的 HTTPS 证书，申请方法请在谷歌浏览器中搜索。
    -   在有 HTTPS 服务之前，请确保 DataV 页面是使用 HTTP 协议打开的。（该策略可确保 HTTPS 网站的安全）
3.  填写数据库信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16538/15584351507911_zh-CN.png)

    -   名称：数据源的显示名称，可以自由命名。
    -   域名：您服务器的IP地址，如果您使用的是ECS服务器，则应该配置为ECS服务器的公网IP。
    -   端口：下载并安装好代码包后，系统会自动生成端口号。
    -   Key：下载并安装好代码包后，系统会自动生成 Key。
    -   Secret：下载并安装好代码包后，系统会自动生成 Secret。

        获取 Key 和 Secret，请参阅[DataV Proxy 使用说明](intl.zh-CN/用户指南/进阶技巧/DataV Proxy 使用说明.md#)。

    -   数据库：当前所选数据库的名称。
    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

4.  测试成功后，单击**确认**，完成数据源添加。

