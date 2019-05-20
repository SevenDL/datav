# Add a Table Store data source {#concept_e42_c5h_wfb .concept}

[Table Store](../../../../reseller.en-US/Product Introduction/What is Table Store?.md#) is a NoSQL database service built on Alibaba Cloud's Apsra distributed operating system.

## Procedure {#section_lnc_fgq_p2b .section}

1.  Choose **Data Sources** \> **Add Source**.
2.  From the **Type** drop-down menu, select **TableStore**.
3.  Enter the Table Store data source information, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155834843032624_en-US.png)

    -   **Name**: The display name of the data source. You can customize the display name as needed.
    -   **AK ID**: The AccessKey ID of the account that can access Table Store.
    -   **AK Secret**: The AccessKey Secret of the account that can access Table Store.
    -   **Internet**: The [endpoint](../../../../reseller.en-US/Product Introduction/Terms/Endpoint.md#) of Table Store. You can enter an endpoint according to the Table Store instance to be accessed.
    The system automatically tests connectivity after the data source information is set.

4.  After the connectivity test is successful, click **OK**.

    The data source is automatically displayed in the data source list.


## Use the Table Store data source {#section_jln_qgz_5fb .section}

1.  In the DataV console, click **Projects**, select the target project, and click **Edit**.
2.  On the displayed page, select a widget. In the data pane, select **TableStore** for **Data Source Type**.
3.  From the **Select Data Source** drop-down menu, select the Table Store data source you have configured before.
4.  From the **Select Action** drop-down menu, select either of the following actions:
    -   getRow: Corresponds to the GetRow API of Table Store. For more information, see [GetRow API](../../../../reseller.en-US/.md#).
    -   getRange: Corresponds to the GetRange API of Table Store. For more information, see [GetRange API](../../../../reseller.en-US/API Reference/Operations/GetRange.md#).
5.  In the **Select Action** area, enter a SQL statement. The SQL statement must meet the following requirements:
    -   Parameters in the SQL statement must be in the JSON format.
    -   If you select getRow, the system reads data from a row according to the specified primary key.

        The following is an example of the parameter format:

        ```
        
        {
        "table_name": "test",
        "rows": {
        "id": 2
        },
        "columns": [
        "id",
        "test"
        ]
        }
        ```

        The parameters in the SQL statement:

        -   table\_name: The name of the table to be queried.
        -   rows: The conditions for filtering a row. Only the rows that meet the conditions are displayed. To add a column as a condition, you must create an index for the column first.
        -   columns: The name of columns to be displayed.
    -   The getRange action is used to read data with specified primary keys. The parameter format is as follows:

        ```
        
        {
        "table_name": "test",
        "direction": "FORWARD",
        "columns": [
        "id",
        "test"
        ],
        "range": {
        "limit": 4,
        "start": {
        "id": "InfMin"
        },
        "end": {
        "id": 3
        }
        }
        }
        ```

        -   table\_name: The name of the table to be queried.
        -   direction: The query sequence.
        -   columns: The name of the column to be displayed.
        -   limit: The maximum number of rows to be displayed.
        -   start: The start column in the displayed result. You must create indexes for the relevant columns.
        -   end: The end column in the displayed result. You must create indexes for the relevant columns.
        **Note:** You can use InfMin and InfMax to indicate the minimum and maximum values of the start and end parameters.

6.  Click **View Data Response** to view the effect.

## Example {#section_vrs_kpt_vfb .section}

1.  Prepare data for the Table Store data source.

     Log on to the [Table Store console](https://ots.console.aliyun.com/), [create an instance](../../../../reseller.en-US/Quick Start/Create an instance.md#), and [read or write data](../../../../reseller.en-US/Quick Start/Read or Write data.md#). In the following example, an instance named test1948 is created. This instance has three rows of data and each row has two columns named id \(primary key in integer format\) and test \(in string format\).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155834843032810_en-US.png)

2.  Configure the data source, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155834843032811_en-US.png)

3.  Query parameters.

    -   getRow:

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155834843032812_en-US.png)

        The data response is as follows.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155834843032813_en-US.png)

    -   getRange:

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155834843032814_en-US.png)

        The data response is as follows.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155834843032815_en-US.png)

    **Note:** When you query the getRange parameter, if you set start to id:InfMin and end to id:3, the values 1 and 2 are displayed for id. The reason for this is that the getRange parameter does not contain the end row, whose id is 3, because it is not within the range specified.


