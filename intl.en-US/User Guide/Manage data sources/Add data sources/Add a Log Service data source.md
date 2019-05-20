# Add a Log Service data source {#concept_z2h_vgt_cgb .concept}

[Log Service](../../../../reseller.en-US/Product Introduction/What is Log Service.md#) \(formerly known as SLS\) is an all-in-one service for real-time data management. With Log Service, you can collect, subscribe, transfer, and search for massive data.

## Procedure {#section_lnc_fgq_p2b .section}

1.  Choose **Data Sources** \> **Add Source**.
2.  From the **Type** drop-down menu, select **Log Service**.
3.  Enter the Log Service data source information, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79886/155834806934422_en-US.png)

    -   **Name**: The display name of the data source. You can customize the display name as needed.
    -   **AppKey**: The AccessKey ID of the account that can access Log Service.
    -   **AppSecret**: The AccessKey Secret of the account that can access Log Service.
    -   **EndPoint**: The endpoint of Log Service. You can enter an endpoint according to the network type and region to which the target Log Service instance belongs. For more information, see [Service endpoint](../../../../reseller.en-US/API Reference/Service endpoint.md#).

        For example, if the network type is VPC, you can set the **EndPoint** in Shanghai region to **https://cn-shanghai-intranet.log.aliyuncs.com**.

    The system automatically tests connectivity after the data source information is set.

4.  After the connectivity test is successful, click **OK**.

    The data source is automatically displayed in the data source list.


## Configure Log Service {#section_blw_bh5_cgb .section}

For more information about how to activate, configure, and use Log Service, see [Log Service](../../../../reseller.en-US/Product Introduction/What is Log Service.md#).

## Use the Log Service data source {#section_jln_qgz_5fb .section}

1.  In the DataV console, click **Projects**, select the target project, and click **Edit**.
2.  On the displayed page, select a widget. In the data pane, select **Log Service** for **Data Source type**.
3.  From the **Select Data Source** drop-down menu, select the Log Service data source you have configured before.
4.  In the **Query** area, enter the query parameters. The parameters support the following formats:
    -   JSON object:

        ```
        {
        "projectName": "test",
        "logStoreName": "access-log",
        "topic": "test",
        "from": 1509897600,
        "to": 1509984000,
        "query": "" ,
        "line": 100,
        "offset": 0
        }
        ```

    -   Query syntax: [Query syntax](../../../../reseller.en-US/User Guide/Index and query/Query/Query syntax.md#).
5.  Click **View Data Response** to view the effect.

