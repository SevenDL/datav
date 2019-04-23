# 添加业务实时监控服务ARMS数据源 {#concept_syl_pw4_1gb .concept}

[业务实时监控服务](https://www.aliyun.com/product/arms)（Application Real-Time Monitoring Service，简称ARMS）是一款APM类的监控产品。用户可基于ARMS的前端、应用和自定义监控功能，快速构建实时的应用性能和业务监控能力。

## 操作步骤 {#section_lnc_fgq_p2b .section}

1.  单击**我的数据** \> **添加数据**。
2.  单击**类型**下拉菜单，选择数据库类型为**业务实时监控服务ARMS**。
3.  填写ARMS相关信息，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334197_zh-CN.png)

    -   **名称**：数据源的显示名称，您可以自由命名。
    -   **AK ID**：拥有ARMS访问权限的账号的AccessKey ID（从ARMS控制台获取）。
    -   **AK Secret**：拥有ARMS访问权限的账号的AccessKey Secret（从ARMS控制台获取）。
4.  信息填写完成后，单击**确定**保存，完成数据源添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用ARMS数据源 {#section_jln_qgz_5fb .section}

1.  在DataV控制台上，单击**我的可视化**，选择您的项目，单击**编辑**，进入大屏编辑界面。
2.  单击选择某一组件，在数据面板中，选择**数据源类型**为**业务实时监控服务**。
3.  单击**选择已有数据源**下拉菜单，选择配置完成的业务实时监控服务数据源 。
4.  在下方**请求URL**编辑框内填写ARMS数据集DataV接入链接 。
5.  单击**查看数据响应结果**，数据响应成功后即可看到效果。

## 调用示例 {#section_vrs_kpt_vfb .section}

参考资料：[ARMS DataV接入演示视频](https://www.aliyun.com/product/arms) 、[ARMS 产品文档](https://help.aliyun.com/product/34364.html)。

1.  [开通ARMS服务](https://help.aliyun.com/document_detail/65257.html) 。
2.  进入[ARMS控制台](https://arms.console.aliyun.com/)，单击**自定义监控-数据源管理** \> **云服务器ECS** \> **同步ECS**。
    -   同步完成后会列出用户账号下的ECS服务器。
    -   对于需要监控的机器，如果**Agent状态**为**未安装**，单击**安装Agent**，根据教程进行安装，安装完成后单击**检查Agent**同步Agent状态。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334199_zh-CN.png)

    -   **Agent状态**为**已安装**的机器可以作为数据源。
3.  单击左侧菜单栏的**自定义监控** \> **监控任务管理**，按照以下步骤新建并配置监控任务。
    1.  选择**新建监控任务** \> **新建自定义任务**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334200_zh-CN.png)

    2.  在新建自定义任务对话框中，填写任务信息，完成后单击**新建并进行配置**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334201_zh-CN.png)

    3.  配置任务。
        1.  配置数据源。

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334202_zh-CN.png)

            1.  选择**日志源类型**为**云服务器ECS**。
            2.  单击**添加日志源**，添加**数据源**和**日志路径**。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334203_zh-CN.png)

                **说明：** 日志路径由logtail的配置决定，此处默认为error日志路径。

            3.  单击**日志抓取预览**，预览日志。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334204_zh-CN.png)

        2.  日志清洗。
            1.  根据业务需求选择切分方案，本案例选择**智能切分**。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334205_zh-CN.png)

            2.  单击**获取方案**，系统自动开始切分，切分完成后可查看切分结果。本案例的切分结果如下：

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902334206_zh-CN.png)

            3.  单击**保存**，保存日志。保存完成后，单击**下一步**，如果出现如下提示框，直接单击**确定**即可。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902434209_zh-CN.png)

        3.  配置数据集与报警。
            1.  单击**添加数据集**，新建数据集。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902434212_zh-CN.png)

            2.  填写数据集信息，单击**保存**。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902434213_zh-CN.png)

            3.  单击**完成配置**，系统会弹出**启动监控任务**对话框，选择**从最新位置消费**，单击**确定**，即可启动监控任务。

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902434214_zh-CN.png)

                任务启动成功后，可查看任务**监控状态**，如下图所示：

                ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902434210_zh-CN.png)

4.  单击左侧菜单栏的**数据集管理** \> **查询数据**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902434215_zh-CN.png)

5.  将查询到的数据接入DataV中。

    单击**接入DataV** \> **生成DataV接入链接**，获取AK和接入链接。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902434243_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902434244_zh-CN.png)

6.  进入DataV控制台，编辑 ARMS 数据源。

    填写从ARMS获取的AK ID和AK Secret。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902534245_zh-CN.png)

7.  在**请求URL**编辑框中输入从ARMS获取到的DataV接入链接。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902534246_zh-CN.png)

8.  单击**查看数据响应结果**，查看ARMS监控数据。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/77557/155599902534247_zh-CN.png)


