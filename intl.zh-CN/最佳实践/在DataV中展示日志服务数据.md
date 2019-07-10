# 在DataV中展示日志服务数据 {#concept_x5d_rcm_q2b .concept}

本文档为您介绍如何使用DataV完成日志服务数据的展示，实现实时业务监控。

## 概述 {#section_ry1_gup_3kn .section}

本案例的整体步骤如下。

1.  [准备工作](#)。
2.  [配置日志服务](#)。
3.  [配置DataV](#)。

## 准备工作 {#section_rp2_vcm_q2b .section}

-   完成[为Kubernetes和日志服务配置Log4JAppender](../../../../intl.zh-CN/用户指南/Kubernetes集群/日志管理/为 Kubernetes 和日志服务配置 Log4JAppender.md#)中的步骤，并且服务运行正常。
-   购买DataV企业版。

## 配置日志服务 {#section_av1_xcm_q2b .section}

1.  登录日志服务控制台，查看Logstore列表。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404098038_zh-CN.png)

2.  单击列表中的**查询**，出现如下界面。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404098039_zh-CN.png)

3.  为所有必填字段创建索引。

    单击页面右上角菜单栏的**查询分析属性**，选择**设置**，为每个项目创建索引。

4.  在**查询分析**页面验证数据。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404098041_zh-CN.png)

5.  数据导入成功后，单击左侧菜单栏的**仪表板**，切换至图形页面（下图中的X轴为时间）。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404098042_zh-CN.png)


## 配置DataV {#section_vq4_pgm_q2b .section}

1.  登录DataV控制台。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404108043_zh-CN.png)

2.  单击**创建项目**，选择一个空白模板并输入项目名称，单击**创建**。
3.  在画布中添加一个组件。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404108045_zh-CN.png)

    该组件默认显示静态数据集。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404108046_zh-CN.png)

4.  单击该组件，在右侧的**数据**配置页签，将**数据源类型**设置为**简单日志服务 SLS**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404108047_zh-CN.png)

5.  单击**新建**。在**添加数据**对话框中，填入数据源相关信息，单击**确定**。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/156274041051174_zh-CN.png)

    -   **数据源名称**：数据源的显示名称，您可以自由命名。
    -   **AppKey**：拥有目标SLS访问权限的账号的AccessKey ID。
    -   **AppSecret**：拥有目标SLS访问权限的账号的AccessKey Secret。
    -   **EndPoint**：填写SLS服务的**EndPoint**。请参考日志[服务入口](../../../../intl.zh-CN/API 参考/服务入口.md#)文档，根据您SLS服务的网络类型和所在区域进行填写。例如VPC网络下，上海区域的**EndPoint**填写为**https://cn-shanghai-intranet.log.aliyuncs.com**。

        **说明：** **Endpoint**前需要添加`http://`或者`https://`。

6.  选择添加完成的数据源，并在数据查询框中输入如下示例脚本进行查询。

    ``` {#codeblock_4vt_bn4_6c5}
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

    **说明：** `from`和`to`是时间戳，可以用来检查**查询**中的原始数据。

7.  单击**查看数据响应结果**预览数据，结果如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404118049_en-US.png)

8.  勾选**使用过滤器**，添加如下的过滤器，确保`pv`为整数，单击**确定**。

    ``` {#codeblock_6b7_v6v_hdx}
    return Object.keys(data).map((key) => {
     let d= data[key];
     d["pv"] = parseInt(d["pv"]);
     return d;
    }
    )
    ```

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404118050_en-US.png)

9.  设置坐标轴并验证是否正确。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404118052_en-US.png)

10. 单击**预览**。

    您可以看到x和y使用正确的数据类型，并且pv为整数。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404128054_en-US.png)

11. 单击界面右上角的**发布**，发布该大屏项目，使得您可以公开访问该大屏。

## 查看结果 {#section_q3s_nhm_q2b .section}

本案例的发布结果如下图所示。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15627404128057_en-US.png)

您已在阿里云上成功配置DataV和Log Service，并使用Log Service通过自定义DataV可视化大屏实现了实时监控。

## 参考文档 {#section_adn_4hm_q2b .section}

有关日志服务和容器服务的更多信息，请参见：

-   [日志服务](https://www.alibabacloud.com/product/log-service)
-   [容器服务](https://www.alibabacloud.com/product/container-service)

