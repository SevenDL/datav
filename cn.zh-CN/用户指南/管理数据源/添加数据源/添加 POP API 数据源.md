# 添加 POP API 数据源 {#concept_cx4_4rw_wfb .concept}

POP API（也称 OPEN API）是阿里云提供的云产品开放接口的调用方式，使用 POP API 可以方便地调用各云产品提供的 API 接口，轻松实现控制、查询等功能。

在 DataV 中，最常见的场景是使用 POP API 调用其他的云产品的API，获取数据并展示出来。

## 操作步骤 {#section_lnc_fgq_p2b .section}

1.  单击**我的数据** \> **添加数据**。
2.  单击**类型**下拉菜单，选择数据库类型为**POP API**。
3.  填写POP API相关信息，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64884/154518927232819_zh-CN.png)

    -   **名称**：数据源的显示名称，您可以自由命名。
    -   **EndPoint**：POP API的服务地址，需要您从云产品的API文档处获取。比如ECS的[中心服务地址](https://help.aliyun.com/document_detail/25489.html)为 `ecs.aliyuncs.com`，云监控的杭州region的[服务地址](https://help.aliyun.com/document_detail/28616.html)为`metrics.cn-hangzhou.aliyuncs.com`。
    -   **APIVersion**：云产品的API版本，您可以从云产品的API文档获取，如云监控的 [API 版本](https://help.aliyun.com/document_detail/28616.html)为`2017-03-01`。
    -   **AppKey**：您可以调用POP API的账号的AccessKey ID。
    -   **AppSecret**：您可以调用POP API的账号的AccessKey Secret。
    数据库信息填写完成后，系统会自动进行测试连接，验证能否正常连通。

4.  测试连接成功后，单击**确认**保存，完成数据源添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用 POP API 数据源 {#section_jln_qgz_5fb .section}

1.  在DataV控制台上，单击**我的可视化**，选择您的项目，单击**编辑**，进入大屏编辑界面。
2.  单击选择某一组件，在数据面板中，选择**数据源类型**为**POP API**。
3.  单击**选择已有数据源**下拉菜单，选择配置完成的POP API数据源 。
4.  **接口名称**：在编辑框中填写需要需要调用的接口名称，即API 调用中的Action参数，取值来自云产品提供的API列表，比如云监控的`QueryMetricList` 。
5.  **返回结果路径**：取POP API返回结果的一部分作为结果返回。

    比如 POP API 返回：

    ```
    {
             "data": [
               {
                 "x": 1,
                 "y": 2
               },
               {
                 "x": 2,
                 "y": 4
               }
              ]
          }
    ```

    如果填写**data**，则数据响应结果为：

    ```
    [
               {
                 "x": 1,
                 "y": 2
               },
               {
                 "x": 2,
                 "y": 4
               }
            ]
    ```

    这个转换可以在过滤器中进行，此处可以留空不填。

6.  在下方的编辑框中输入查询参数，参数说明如下：

    -   查询参数为 POP API 的接口参数，以 JSON 对象的形式填写。
    -   参数名参考云产品 API 的入参说明。
    -   回调 id 在 JSON 对象的 value 中填写。
    以云监控的[QueryMetricList](https://help.aliyun.com/document_detail/51936.html) API为例：

    ```
    // 使用回调 id: myInstanceId
                {
                  "Period": 600,
                  "StartTime": "2018-11-20 11:30:00",
                  "EndTime": "2018-11-21 11:30:00",
                  "Metric": "cpu_idle",
                  "Project": "acs_ecs_dashboard",
                  "Dimensions": "{instanceId:':myInstanceId'}"
                }
    ```

7.  单击**查看数据响应结果**，数据响应成功后即可看到效果。

