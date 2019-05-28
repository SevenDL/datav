# 添加 RDS for MySQL 数据源 {#concept_xdt_blp_p2b .concept}

## 通过内网添加数据源 {#section_t1g_hmq_p2b .section}

-   **操作步骤** 
    1.  登录[DataV控制台](https://datav.alibabacloud.com/)，选择**我的数据** \> **添加数据**。
    2.  单击**类型**下拉箭头，选择数据库类型为 **RDS for MySQL**。
    3.  单击下拉箭头，选择**内网**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15590145247824_zh-CN.png)

    4.  填写数据库信息。

        数据库类的连接目前支持**华东1**、**华东2**和**华北2**的阿里云内网 IP 连接，以及公网 IP 连接，目前不支持 IP 白名单。

        如果需要新建数据库，请参阅[创建数据库](https://www.alibabacloud.com/help/doc-detail/26190.htm)。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15590145247826_zh-CN.png)

        -   名称：数据源的显示名称，可以自由命名。
        -   域名：连接数据库的 URL 地址（不是官网页面的 URL，也不是本机的 IP，是需要 DataV 服务器能够通过公网或阿里云部分 Region 内网访问数据库的 URL 地址）。

            例如使用内网环境下的阿里云RDS for MySQL，域名示例为：**rm-bpxxxxxxxxx33150.mysql.rds.aliyuncs.com**，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。

        -   用户名：登陆数据库的用户名。
        -   密码：登陆数据库的密码。
        -   端口：数据库设置的端口。
        -   数据库：当前所选数据库的名称。
        数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

    5.  测试连接通过后，单击**确认**，完成数据源添加。

        新添加的数据源会自动列在数据源列表中。


## 通过外网添加数据源 {#section_hq4_hqq_p2b .section}

-   **操作步骤** 
    1.  登录[DataV控制台](https://datav.alibabacloud.com/)，选择**我的数据** \> **添加数据**。
    2.  单击**类型**下拉箭头，选择数据库类型为 **RDS for MySQL**。
    3.  单击下拉箭头，选择**外网**。

        如果需要设置外网地址，请参阅[设置内外网地址](https://www.alibabacloud.com/help/doc-detail/26195.htm)。

    4.  填写数据库信息。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15590145247829_zh-CN.png)

        -   名称：数据源的显示名称，可以自由命名。
        -   域名：连接数据库的 URL 地址（不是官网页面的 URL，也不是本机的 IP，是需要 DataV 服务器能够通过公网或阿里云部分 Region 内网访问数据库的 URL 地址）。

            例如使用外网环境下的阿里云RDS for MySQL，域名示例为：**rm-bpxxxxxxxxxco.mysql.rds.aliyuncs.com**，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。

        -   用户名：登陆数据库的用户名。
        -   密码：登陆数据库的密码。
        -   端口：数据库设置的端口。
        -   数据库：当前所选数据库的名称。
        数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

    5.  测试连接通过后，单击**确认**，完成数据源添加。

        新添加的数据源会自动显示在数据源列表中。


