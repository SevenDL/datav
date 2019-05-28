# 添加 Elasticsearch 数据源 {#concept_303795 .concept}

Elasticsearch 数据源提供了100%兼容开源 Elasticsearch 的功能，以及 Security、Machine Learning、Graph、APM 等商业功能，致力于数据分析、数据搜索等场景服务。本文档为您介绍在 DataV 中添加并使用 Elasticsearch 数据源的方法，帮助您快速地使用 Elasticsearch 数据源完成数据分析和搜索结果的大屏展示。

## 操作步骤 {#section_w0w_vfw_w7w .section}

1.  登录 [DataV 控制台](http://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉箭头，选择数据类型为 **Elasticsearch**。
3.  在添加数据对话框中填写 Elasticsearch 数据服务项目信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/248997/155901497647872_zh-CN.png)

    **说明：** 在使用 Elasticsearch 数据源之前，需要先授权 DataV 对阿里云 Elasticsearch 数据服务的访问。

    在添加数据对话框中，单击**使用前请授权 DataV 访问**，跳转到授权页面，单击**同意授权**完成授权访问。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/248997/155901497747881_zh-CN.png)

    -   **自定义数据源名称**：数据源的显示名称，可以自由命名。
    -   **Region**：Elasticsearch 实例的地域（默认选择**华东1区**）。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/248997/155901497747903_zh-CN.png)

    -   **实例ID**：用于查询可用的 Elasticsearch 实例 ID。授权 DataV 访问 Elasticsearch 后，单击**获取实例列表**可以获取到 Elasticsearch 的实例列表，单击右侧下拉框选择列表中某一实例（或直接输入数据库名称选择已有实例）。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/248997/155901497747904_zh-CN.png)

        请参考[基本信息](../../../../cn.zh-CN/用户指南/实例管理/基本信息.md#)获取 Elasticsearch 实例的 ID。

    -   **密码**：所选 Elasticsearch 实例在被创建时设置的密码，不同实例的密码不同。

        请参考[密码配置](../../../../cn.zh-CN/快速入门/购买界面参数.md#section_qhh_44l_zgb)获取 Elasticsearch 实例的密码。

    配置成功后，系统会自动进行测试连接。

4.  测试连接成功后，单击**确定**，完成数据源添加。

## 使用 Elasticsearch 数据源 {#section_nfj_mwp_tv3 .section}

在使用 Elasticsearch 数据源之前，请先完成 [Elasticsearch 数据源的添加](#section_w0w_vfw_w7w)。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/248997/155901497747894_zh-CN.png)

1.  在 DataV 控制台上，单击**我的可视化**，选择您的项目，单击**编辑**，进入大屏编辑界面。
2.  单击选择某一组件，在数据面板中，选择**数据源类型**为 **Elasticsearch**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/248997/155901497747902_zh-CN.png)

3.  单击**选择已有数据源**下拉菜单，选择您已经添加的 Elasticsearch 数据源 。
4.  在 **index** 输入框中填写查询索引，通常是一个字符串。
5.  在 **Query** 输入框中填写查询体，查询体为 JSON 对象，默认是 \{\} 。
6.  单击**查看数据响应结果**，数据响应成功后即可看到效果。

