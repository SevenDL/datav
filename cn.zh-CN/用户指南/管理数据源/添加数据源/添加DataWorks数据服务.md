# 添加DataWorks数据服务 {#concept_dj2_g4z_ngb .concept}

本文为您展示了如何在DataV中添加**DataWorks数据服务**数据源，并将通过DataWorks数据表生成的API，快速地展示在DataV可视化大屏中。

## 操作步骤 {#section_eng_2hr_p2b .section}

1.  使用HTTP协议进入[DataV控制台](http://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉箭头，选择数据类型为 **DataWorks 数据服务**。
3.  在添加数据对话框中填写DataWorks 数据服务项目信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/117723/154831922437989_zh-CN.png)

    -   **自定义数据源名称**：数据源的显示名称，可以自由命名。
    -   **项目**：DataWorks项目（工作空间）。
    -   **AppKey**：拥有DataWorks数据服务中某一项目访问权限的账号的AppKey ID，用于API调用（从DataWorks数据服务台获取）。
    -   **AppSecret**：拥有DataWorks数据服务中某一项目访问权限的账号的AppSecret（从DataWorks数据服务台获取）。
    **说明：** 

    获取**AppKey**和**AppSecret**：在[DataWorks数据服务控制台](http://ds-cn-shanghai.data.aliyun.com)中，单击**服务管理** \> **API调用**，可获取您的**AppKey**和**AppSecret**，如下图所示：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/117723/154831922437990_zh-CN.png)

4.  测试成功后，单击**确定**，完成数据源添加。

## 使用DataWorks数据源 {#section_vrs_kpt_vfb .section}

1.  准备通过**DataWorks 数据服务**生成的API数据。
    1.  登录[DataWorks数据服务控制台](http://ds-cn-shanghai.data.aliyun.com)。
    2.  参考[生成API](https://help.aliyun.com/document_detail/73268.html)，使用数据服务生成API。
2.  在DataV控制台上，单击**我的可视化**，选择您的项目，单击**编辑**，进入大屏编辑界面。
3.  单击选择某一组件，在数据面板中，选择**数据源类型**为**DataWorks 数据服务**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/117723/154831922437992_zh-CN.png)

4.  单击**选择已有数据源**下拉菜单，选择您已经添加的DataWorks 数据服务数据源 。
5.  在下方**选择API**下拉框中，单击下拉箭头选择第一步中生成的DataWorks数据服务API 。
6.  单击**查看数据响应结果**，数据响应成功后即可看到效果。

