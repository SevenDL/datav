# Add data {#concept_vzj_vtq_p2b .concept}

## Add data for the map {#section_u5h_gbr_p2b .section}

1.  On the project, click the map widget.
2.  Click the **Data** pane.
3.  On the **Child Management** tab page, click **Isosurface Layer**.

    The data used in this example is obtained from all across China. You can use the data directly or modify the data as needed.

4.  Click **Interpolation Points Data**.
5.  Configure the data.
    -   **Data Source Type**: The APIs have been specified in [Process the APIs](reseller.en-US/Best Practices/Use DataV to view air quality changes before and after the Spring Festival/Preparations/Process the APIs.md#) and the data has been tested. Therefore, set the data source type to API.
    -   **URL**: Enter the API test URL \(http://127.0.0.1:8888/aqi?date=2017012722\).
6.  Click **View Data Response**. The data response is displayed and the data has been successfully matched.
7.  Set the style of the isosurface layer widget.
    1.  Click the **Configuration** pane.
    2.  Set the **Pixel Size**. The recommended value is **3**.

        Setting larger values for the pixel size allows interpolation to work faster, but also reduces the precision of interpolation results.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17486/15585762109288_en-US.png)

    3.  Set the **Render Type**. The recommended type is **Linear**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17486/15585762109289_en-US.png)

    4.  Set the **Classify Color Count**. The recommended value is **35**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17486/15585762109290_en-US.png)


## Add data for the timeline {#section_fzx_xbr_p2b .section}

1.  On the project, click the timeline widget.
2.  Click the **Data** pane.
3.  Set **Data Source Type** to **Static Data**.
4.  Create the required data according to the examples and replace the static data on the data pane of the timeline widget.

    For example, you can use the data obtained each day at 22:00 from January 22, 2017 to February 2, 2017 as the timeline data.

    ```
    [
    {
     "name": "22:00, January 22, 2017",
     "date": 2017012222,
     "value": 2017012222
    },
    {
     "name": "22:00, January 23, 2017",
     "date": 2017012322,
     "value": 2017012322
    },
    {
     "name": "22:00, January 24, 2017",
     "date": 2017012422,
     "value": 2017012422
    },
    {
     "name": "22:00, January 25, 2017",
     "date": 2017012522,
     "value": 2017012522
    },
    {
     "name": "22:00, January 26, 2017",
     "date": 2017012622,
     "value": 2017012622
    },
    {
     "name": "22:00, January 27, 2017",
     "date": 2017012722,
     "value": 2017012722
    },
    {
     "name": "22:00, January 28, 2017",
     "date": 2017012822,
     "value": 2017012822
    },
    {
     "name": "22:00, January 29, 2017",
     "date": 2017012922,
     "value": 2017012922
    },
    {
     "name": "22:00, January 30, 2017",
     "date": 2017013022,
     "value": 2017013022
    },
    {
     "name": "22:00, January 31, 2017",
     "date": 2017013122,
     "value": 2017013122
    },
    {
     "name": "22:00, February 1, 2017",
     "date": 2017020122,
     "value": 2017020122
    },
    {
     "name": "22:00, February 1, 2017",
     "date": 2017020222,
     "value": 2017020222
    }
    ]
    ```

    -   name: displayed content in a node of the timeline
    -   date: date in the timeline, which can be used as a callback ID
    -   value: date in the timeline
5.  Set the timeline style.
    1.  Click the **Configuration** pane.
    2.  Click **Node** and set **Data Format** to **%Y%m%d%H**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17486/15585762109291_en-US.png)

    3.  Click **Interaction** and set the value of the callback ID to date.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17486/15585762109292_en-US.png)


## Set the map title {#section_y15_ccr_p2b .section}

1.  On the project, click the title widget.
2.  Click the **Data** pane.
3.  Set **Data Source Type** to **Database**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17486/15585762119293_en-US.png)

4.  In the **Select Data Source** list, select a database.

    If no database is available, you can click **Create** to create a database as promoted. For more information about how to create a database, see [Configure data sources](../../../../reseller.en-US/User Guide/Manage data sources/Add data sources/Overview.md#).

5.  Enter the following command in the SQL area:

    ```
    select to_char(to_timestamp(:date,'YYYYMMDDHH24'),'YYYY (year) mm (month) DD (day) HH (24-hour format)')||'air quality' as value;
    ```

    `:date`: actual value corresponding to the callback ID


You can also add legends as needed. The following figure shows the display effect of the project.

![](images/9294_en-US.gif)

