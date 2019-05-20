# 在 DataV 中调用数据服务 API {#task_sdl_nfg_qgb .task}

本文为您介绍如何在 DataV 中调用 DataWorks 的数据服务 API，并将数据返回结果展示在 DataV 大屏中。

在开始本案例前，您需要首先完成[准备工作](cn.zh-CN/最佳实践/DataV 调用 DataWorks 数据服务 API 展示数据成果/准备工作.md#)，并已经[生成了数据服务 API](cn.zh-CN/最佳实践/DataV 调用 DataWorks 数据服务 API 展示数据成果/实施步骤/使用 DataWorks 数据服务生成 API.md#)。

**说明：** 您必须使用 HTTP 协议进入 DataV 控制台，否则会导致 API 数据响应失败。

通过 DataV 调用数据服务 API 主要包含以下二个步骤：

1.  [添加 DataWorks 数据源](#)：在 DataV 中添加 DataWorks 数据源。
2.  [在大屏中调用数据服务 API](#)：在组件的数据配置中，配置 API 数据源参数。

1.  添加 DataWorks 数据源。 
    1.  使用 HTTP 协议进入 [DataV 控制台](http://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
    2.  单击**类型**下拉箭头，选择数据类型为 **DataWorks 数据服务**。
    3.  在添加数据对话框中填写 DataWorks 数据服务项目信息，本案例的配置信息如下图所示。 

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/155833924638528_zh-CN.png)

        -   **自定义数据源名称**：数据源的显示名称，可以自由命名。
        -   **项目**：DataWorks 项目（工作空间）。
        -   **Region**：需要与您的 DataWorks 项目在同一Region下。
        -   **AppKey**/**AppSecret**：拥有 DataWorks 数据服务中某一项目访问权限的账号的 AppKey 和 AppSecret，用于 API 调用。获取方式请参考[使用 DataWorks 数据服务生成 API 中的第三步](cn.zh-CN/最佳实践/DataV 调用 DataWorks 数据服务 API 展示数据成果/实施步骤/使用 DataWorks 数据服务生成 API.md#step3)。
2.  在大屏中调用数据服务 API。 
    1.  在 DataV 控制台中，单击**我的可视化** \> **新建可视化**。
    2.  选择一个模板，单击**创建**，输入大屏名称，再次单击**创建**。 本案例选择**企业实时销售数据**模板。模板中的组件自带了静态数据，本案例以模板中的**基本折线图**组件为例，将组件数据配置为[查询成交金额增长趋势的 API](cn.zh-CN/最佳实践/DataV 调用 DataWorks 数据服务 API 展示数据成果/实施步骤/使用 DataWorks 数据服务生成 API.md#)。
    3.  单击模板中的**基本折线图**组件，在右侧的数据配置面板中，选择**数据源类型**为 **DataWorks 数据服务**，**已有数据源**为您第一步中添加的数据源，**API** 为您已经发布的 API，本案例的配置如下图所示。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/155833924638573_zh-CN.png)

 

        **说明：** 本案例将上图中的 pageSize 设置为5，以查询 5 天的数据。

    4.  单击**查看数据响应结果**，查看 API 的查询结果，如下图所示。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/155833924638576_zh-CN.png)


    5.  在字段映射关系中，将 x 字段映射为 date1（日期为 x 轴），y 字段映射为 amount（成交额为 y 轴）。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/155833924638577_zh-CN.png)

 

        **说明：** 配置完成后，可以看到，当前 x 和 y 无法匹配到字段。这是由于 DataV 对数据格式有一定要求，不能识别结构较深的字段，因此这里要添加一个数据过滤器，过滤掉不必要的字段，在本案例中直接返回 rows 数组即可。

    6.  勾选**使用过滤器**，单击**添加过滤器** \> **新建过滤器**，在过滤函数中输入 `return data.data.rows;`，单击**预览**，预览成功后，单击**完成**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/155833924638578_zh-CN.png)

 数据过滤器支持使用 JavaScript 代码对数据结果进行二次过滤和处理，过滤器的 data 参数为 API 返回结果的 JSON 对象。本案例中，我们只需要返回 API 结果中的 rows 数组，故只需要输入代码 `return data.data.rows;` 即可，过滤完成后可以看到数据匹配成功。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/155833924738581_zh-CN.png)

        **说明：** 此时折线图并没有正确展示，由于 API 返回的日期格式与组件默认的格式不一样，因此您还需要设置 x 轴的**轴标签**样式。

    7.  切换到组件的**配置**面板，设置 x 轴**轴标签**的**数据种类**为**类目型**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/155833924738583_zh-CN.png)

 组件的样式和数据都配置完成后，可以看到组件使用 API 数据，且显示正常。

按照以上方法，可以配置其他组件的数据和样式，完成大屏制作。大屏制作完成后，可进行[预览](../../../../cn.zh-CN/用户指南/管理可视化应用/预览可视化应用.md#)和[发布](../../../../cn.zh-CN/用户指南/管理可视化应用/发布可视化应用.md#)，最终得到一个您满意的可视化大屏。

