# 在DataV中展示日志服务数据 {#concept_x5d_rcm_q2b .concept}

本文档描述了如何配置 DataV，完成日志服务数据渲染。

主要包括以下内容：

-   创建并配置日志服务，并应用在DataV中（设置索引）。
-   创建大屏项目。
-   发布大屏项目。

## 前提条件 {#section_rp2_vcm_q2b .section}

-   您已经完成了[为 Kubernetes 和日志服务配置 Log4JAppender](../../../../intl.zh-CN/用户指南/Kubernetes集群/日志管理/为 Kubernetes 和日志服务配置 Log4JAppender.md#)中的步骤，并且服务运行正常。
-   您已经购买了DataV企业版。

## 配置日志服务 {#section_av1_xcm_q2b .section}

1.  登录日志服务控制台，查看 Logstore 列表。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448038_zh-CN.png)

2.  单击列表中的**查询**，出现如下界面。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448039_zh-CN.png)

3.  为所有必填字段创建索引。下图中为每个项目创建索引，单击界面右上角菜单栏的**查询分析属性**，选择**设置**。
4.  在**查询分析**页面验证数据，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448041_zh-CN.png)

5.  数据导入成功后，单击左侧菜单栏的**仪表板**，切换到图形界面（下图中X轴为时间）。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448042_zh-CN.png)


## 配置 DataV {#section_vq4_pgm_q2b .section}

1.  登录 DataV 控制台。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448043_zh-CN.png)

2.  单击**创建项目**，选择一个空白模板并输入项目名称，单击**创建**。
3.  在画布中添加一个组件。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448045_zh-CN.png)

    该组件默认显示静态数据集。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448046_zh-CN.png)

4.  单击该组件，在右侧的**数据**配置页签，将**数据源类型**设置为**简单日志服务 SLS**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448047_zh-CN.png)

5.  单击**选择配置**下的**新建**。出现**新建数据**对话框，填入相关信息，单击**完成**。

    **说明：** 确认在 **Endpoint** 前加了 `http://` 或者 `https://`。

6.  添加数据完成后，选择新建的配置，并使用以下示例进行查询。

    ```
    {
    "projectName": "k8s-logs",
    "logStoreName": "k8s-logstore",
    "topic": "",
    "from": "1518883200",
    "to": "1518969600",
    "query": "* | select count(1) as pv, date_format(from_unixtime(__time__ - __time__%3600) ,'%Y/%m/%d %H:%i:%s')   as time group by time  order by time limit 1000" ,
    "line": 100,
    "offset": 0
    }
    ```

    **说明：** from 和 to 是时间戳，可以用来检查**查询**中的原始数据。

7.  单击**查看数据响应结果**预览数据，结果如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448049_en-US.png)

8.  勾选**使用过滤器**，添加如下的过滤器，确保 `pv` 为整数，单击**确定**。

    ```
    return Object.keys(data).map((key) => {
     let d= data[key];
     d["pv"] = parseInt(d["pv"]);
     return d;
    }
    )
    ```

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098448050_en-US.png)

9.  设置坐标轴并验证是否正确。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098458052_en-US.png)

10. 单击**预览**。

    您可以看到 x 和 y 使用正确的数据类型，并且 pv 为整数。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098458054_en-US.png)

11. 单击界面右上角的**发布**，发布该大屏项目，使得用户可以公开访问。

    发布结果如下所示：

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584098458057_en-US.png)


## 结论 {#section_q3s_nhm_q2b .section}

您已在阿里云上成功配置 DataV 和 Log Service，并使用 Log Service 通过自定义DataV可视化大屏实现实时监控。

## 相关链接 {#section_adn_4hm_q2b .section}

有关日志服务和容器服务的更多信息，请参见：

-   [日志服务](https://www.alibabacloud.com/product/log-service)
-   [容器服务](https://www.alibabacloud.com/product/container-service)

