# 创建DataHub项目 {#task_dyg_dxh_ffb .task}

阿里云流数据处理平台DataHub是流式数据（Streaming Data）的处理平台，提供对流式数据的发布（Publish），订阅（Subscribe）和分发功能，让您可以轻松构建基于流式数据的分析和应用。

您已经完成了[RDS for MySQL数据库的创建](ZH-CN_TP_21748_V4.dita#task_srh_hxh_ffb)。

1.  登录[阿里云DataHub控制台](https://datahub.console.aliyun.com/)。
2.  在**项目管理**中，选择**华东2**，单击**创建Project**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21747/156015799912592_zh-CN.png)


3.  选择项目右侧的**查看**，单击**创建Topic**。
4.  在**创建Topic**页面，输入**Topic名称**及**Schema**，单击**创建**，如下图所示。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21747/156015800012593_zh-CN.png)


5.  选择Topic右侧的**查看**，单击页面右上角的**+ DataConnector**，选择**同步到RDS Mysql**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21747/156015800012594_zh-CN.png)


6.  在**创建DataConnector**页面，输入RDS for MySQL数据库的相关信息，如下图所示。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21747/156015800012596_zh-CN.png)

 

    -   **Mysql Host**：为您RDS数据库的内网地址。
    -   **Mysql Port**：为您RDS数据库的端口号，一般为3306。
    -   **Mysql Database**：为您RDS数据库的名称。
    -   **Mysql Table**：为您RDS数据库表的名称。
    -   **User**：为您登录RDS数据库的账号。
    -   **Password**：为您登录RDS数据库的密码。
    您可以单击RDS实例链接，获取以上数据库信息。


