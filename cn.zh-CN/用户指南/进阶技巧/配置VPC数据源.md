# 配置VPC数据源 {#concept_o1n_tj1_r2b .concept}

本文档为您介绍在DataV中配置VPC数据源的方法。通过VPC数据源的配置，您可以将[VPC（专有网络）](../../../../cn.zh-CN/产品简介/什么是专有网络.md#)内的数据库接入到DataV中，并作为组件的数据源进行大屏展示。

## 操作步骤 {#section_maf_w5y_gpr .section}

1.  登录[DataV控制台](http://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉箭头，选择数据库类型为**RDS for MySQL**。
3.  单击下拉箭头，选择**内网**。
4.  打开**VPC**开关，并填写数据库信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15614529169304_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15614529179305_zh-CN.png)

    除了传统的数据库配置外，您还需要配置数据库的**VPC ID**和**实例ID**。这两种ID都可以在阿里云控制台中获取。

    -   通过[RDS控制台](https://rdsnext.console.aliyun.com/)获取**VPC ID**和**实例ID**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15614529178636_zh-CN.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15614529178637_zh-CN.png)

    -   如果您的数据库安装在VPC内的ECS上，则需要配置该ECS的**VPC ID**和**实例ID**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15614529178638_zh-CN.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16581/15614529178639_zh-CN.png)

    配置完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

5.  测试连接通过后，单击**完成**，完成数据源添加。

    配置完成后您就可以使用该VPC内的数据库作为组件的数据源了。


