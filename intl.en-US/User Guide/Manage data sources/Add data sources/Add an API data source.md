# Add an API data source {#concept_cx4_4rw_wfb .concept}

An API is provided by Alibaba Cloud to call other APIs. In DataV, this API is often used to call other Alibaba Cloud APIs to obtain and display data.

## Procedure {#section_lnc_fgq_p2b .section}

1.  Choose **Data Sources** \> **Add Source**.
2.  From the **Type** drop-down menu, select **POP API**.
3.  Enter the API data source information, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64884/155834830332819_en-US.png)

    -   **Name**: The display name of the data source. You can customize the display name as needed.
    -   **EndPoint**: The endpoint of the POP API. You can obtain an endpoint from the API documents of Alibaba Cloud products. For example, the [default endpoint](../../../../reseller.en-US/API Reference/Getting started/Request structure.md#) of ECS is `ecs.aliyuncs.com`, and the [endpoint](../../../../reseller.en-US/API Reference/Call API operations.md#) of CloudMonitor in Hangzhou region is `metrics.cn-hangzhou.aliyuncs.com`.
    -   **APIVersion**: The API version of an Alibaba Cloud product. You can obtain an API version from the API documents. For example, the [API version](../../../../reseller.en-US/API Reference/Call API operations.md#) of CloudMonitor is `2017-03-01`.
    -   **AppKey**: The AccessKey ID of the account that can call the POP API.
    -   **AppSecret**: The AccessKey Secret of the account that can call the POP API.
    The system automatically tests connectivity after the data source information is set.

4.  After the connectivity test is successful, click **OK**.

    The data source is automatically displayed in the data source list.


## Use the API data source {#section_jln_qgz_5fb .section}

1.  In the DataV console, click **Projects**, select the target project, and click **Edit**.
2.  On the displayed page, select a widget. In the data pane, select **POP API** for **Data Source Type**.
3.  From the **Select Data Source** drop-down menu, select the POP API data source you have configured before.
4.  In the **Interface Name** dialog box, enter the target API name \(that is, the value of the Action parameter\). You can obtain an API name from the API list of an Alibaba Cloud product, such as `QueryMetricList` of CloudMonitor.
5.  In the **Path of Responses** dialog box, enter part of the POP API response.

    The following is an example of the POP API response:

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

    If you enter **data**, the data response is as follows:

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

    You can leave this field empty and convert data by using the data filter as needed.

6.  Set the query parameters.

    -   The parameters must be POP API parameters and in the JSON object format.
    -   You must set the parameter names according to the input parameters of Alibaba Cloud APIs.
    -   You must set the callback ID in the value of a JSON object.
    The following is an example of how to use the [QueryMetricList](../../../../reseller.en-US/API Reference/Query monitoring data/QueryMetricList.md#) API of CloudMonitor:

    ```
    // Use the callback ID: myInstanceId
                {
                  "Period": 600,
                  "StartTime": "2018-11-20 11:30:00",
                  "EndTime": "2018-11-21 11:30:00",
                  "Metric": "cpu_idle",
                  "Project": "acs_ecs_dashboard",
                  "Dimensions": "{instanceId:':myInstanceId'}"
                }
    ```

7.  Click **View Data Response** to view the effect.

