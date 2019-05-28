# 添加对象存储OSS数据源 {#concept_bgl_qcv_vfb .concept}

[阿里云对象存储服务](../../../../intl.zh-CN/产品简介/什么是对象存储 OSS.md#)（Object Storage Service，简称OSS）为您提供基于网络的数据存取服务。使用OSS，您可以通过网络随时存储和调用文本、图片、音频和视频等各种非结构化数据文件。

## 操作步骤 {#section_lnc_fgq_p2b .section}

1.  登录[DataV控制台](http://datav.alibabacloud.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉菜单，选择数据库类型为**对象存储 OSS**。
3.  填写OSS相关信息，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64454/155901480632329_zh-CN.png)

    -   **名称**：数据源的显示名称，您可以自由命名。
    -   **AK ID**：拥有目标OSS访问权限的账号的AccessKey ID。
    -   **AK Secret** ：拥有目标OSS访问权限的账号的AccessKey Secret 。
    -   **Region** ：目标OSS的Region信息，您可以进入[OSS控制台](https://oss.console.aliyun.com/)，单击您的Bucket名称进行获取。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64454/155901480632341_zh-CN.png)

        上图中的OSS Bucket位于上海区域，所以**region**填写为**oss-cn-shanghai**。

4.  信息填写完成后，单击**确定**保存，完成数据源添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用OSS数据源 {#section_jln_qgz_5fb .section}

1.  在DataV控制台上，单击**我的可视化**，选择您的项目，单击**编辑**，进入大屏编辑界面。
2.  单击选择某一组件，在数据面板中，选择**数据源类型**为**对象存储 OSS**。
3.  单击**选择已有数据源**下拉菜单，选择配置完成的对象存储 OSS数据源 。
4.  在下方**文件路径**编辑框内填写需要的文件路径，内容格式要求如下：
    -   文件必须为json文本格式。
    -   文件路径格式：oss://bucket/file，比如您的Bucket名为myBucket，文件为test.json，应该填写**oss://myBucket/test.json**。
5.  单击**查看数据响应结果**，数据响应成功后即可看到效果。

