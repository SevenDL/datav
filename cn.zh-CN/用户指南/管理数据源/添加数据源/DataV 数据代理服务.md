# DataV 数据代理服务 {#concept_ltx_glp_p2b .concept}

如果您想使用DataV连接自建数据库，就需要暴露数据库的公网 IP 。DataV当前不支持 IP 白名单，如果担心安全性问题，可以使用阿里云提供的数据连接代理服务。

## 操作步骤 {#section_eng_2hr_p2b .section}

1.  进入[DataV控制台](https://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉箭头，选择数据库类型为 **DataV 数据代理服务**。
3.  填写数据库信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16538/15439988877911_zh-CN.png)

    -   名称：数据源的显示名称，可以自由命名。
    -   域名：您服务器的IP地址，如果您使用的是ECS服务器，则应该配置为ECS服务器的公网IP。
    -   端口：下载并安装好代码包后，系统会自动生成端口号。
    -   Key：下载并安装好代码包后，系统会自动生成 Key。
    -   Secret：下载并安装好代码包后，系统会自动生成 Secret。

        获取 Key 和 Secret，请参阅[Linux下配置 DataV Proxy](cn.zh-CN/用户指南/进阶技巧/Linux下配置DataV Proxy.md#)。

    -   数据库：当前所选数据库的名称。
    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

4.  测试成功后，单击**确认**，完成数据源添加。

