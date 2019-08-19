# 使用DataV大屏展示数据返回结果 {#task_sdl_nfg_qgb .task}

本文为您介绍如何在DataV中调用DataWorks的数据服务API，并将数据返回结果展示在DataV大屏中。

在开始本案例前，您需要首先完成[准备工作](cn.zh-CN/最佳实践/DataV调用DataWorks数据服务API展示数据成果/准备工作.md#)，并已经[生成了数据服务API](cn.zh-CN/最佳实践/DataV调用DataWorks数据服务API展示数据成果/使用DataWorks数据服务生成API.md#)。

**警告：** 您必须使用HTTP协议进入DataV控制台，否则会导致API数据响应失败。

通过DataV调用数据服务API主要包含以下二个步骤。

1.  [添加DataWorks数据源](#)：在DataV中添加DataWorks数据源。
2.  [在大屏中调用数据服务API](#)：在组件的数据配置中，配置API数据源参数。

1.  添加DataWorks数据源。 
    1.  使用HTTP协议进入[DataV控制台](http://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
    2.  单击**类型**下拉箭头，选择数据类型为**DataWorks数据服务**。
    3.  在添加数据对话框中填写DataWorks数据服务项目信息，本案例的配置信息如下图所示。 

        ![创建数据源](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/156620386138528_zh-CN.png)

        |参数|说明|
        |--|--|
        |**自定义数据源名称**|数据源的显示名称，可以自由命名。|
        |**项目**|DataWorks项目（工作空间）。|
        |**Region**|需要与您的DataWorks项目在同一Region下。|
        |**AppKey**/**AppSecret**|参考[使用DataWorks数据服务生成API中的第三步](cn.zh-CN/最佳实践/DataV调用DataWorks数据服务API展示数据成果/使用DataWorks数据服务生成API.md#step3)，获取**AppKey**和**AppSecret**。|

2.  在大屏中调用数据服务API。 
    1.  在DataV控制台中，单击**我的可视化** \> **新建可视化**。
    2.  选择一个模板，单击**创建**。
    3.  在创建数据大屏对话框中，输入**数据大屏名称**，单击**创建**。 本案例选择**企业实时销售数据**模板。模板中的组件自带了静态数据，本案例以模板中的**基本折线图**组件为例，将组件数据配置为[查询成交金额增长趋势的API](cn.zh-CN/最佳实践/DataV调用DataWorks数据服务API展示数据成果/使用DataWorks数据服务生成API.md#)。
    4.  单击模板中的**基本折线图**组件，在右侧的数据配置面板中，单击**配置数据源**。
    5.  在设置数据源页面中，选择**数据源类型**为**DataWorks数据服务**，**已有数据源**为您第一步中添加的数据源，**API**为您已经发布的API。![添加数据源](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/156620386138573_zh-CN.png)

 

        **说明：** 本案例将上图中的pageSize设置为5，表示查询5天的数据。

    6.  单击**预览数据源返回结果**，查看API的查询结果，如下图所示。![查看数据源返回结果](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/156620386138576_zh-CN.png)


    7.  返回组件的数据面板，在字段映射关系中，将x字段映射为date1（日期为x轴），y字段映射为amount（成交额为y轴）。![映射字段关系](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/156620386138577_zh-CN.png)

 

        **说明：** 配置完成后，可以看到，当前x和y无法匹配到字段。这是由于DataV对数据格式有一定要求，不能识别结构较深的字段。因此需要添加一个数据过滤器，过滤掉不必要的字段，在本案例中直接返回rows数组即可。

    8.  在组件的数据面板中，勾选**数据过滤器**，单击**添加过滤器**。
    9.  在设置数据源页面中，单击**添加过滤器**右侧的**+**。
    10. 在过滤器代码编辑框中输入`return data.data.rows;`，单击**测试**（需要开启过滤器调试功能）。测试成功后，单击**保存** \> **完成**。![添加数据过滤器](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/156620386238578_zh-CN.png)

 数据过滤器支持使用JavaScript代码对数据结果进行二次过滤和处理，过滤器的data参数为API返回结果的JSON对象。本案例中，您只需要返回API结果中的rows数组，故需要输入代码`return data.data.rows;`即可，过滤完成后可以看到数据匹配成功。

        ![数据匹配成功](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/156620386238581_zh-CN.png)

        **说明：** 此时折线图并没有正确展示，由于API返回的日期格式与组件默认的格式不一样，因此您还需要设置x轴的**轴标签**样式。

    11. 切换到组件的**配置**面板，设置x轴**轴标签**的**数据种类**为**类目型**。![设置x轴的轴标签样式](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/123012/156620386238583_zh-CN.png)

 组件的样式和数据都配置完成后，可以看到组件使用API数据，且显示正常。

按照以上方法，可以配置其他组件的数据和样式，完成大屏制作。

