# Frequently asked questions \(User self-check process\) {#concept_x1q_grv_1fb .concept}

## What is the relationship between the data series and the style series? {#section_a4x_wrk_q2b .section}

-   Data series:

    Most basic two-dimensional widgets such as line charts and bar charts support multiple series. You can set the s field to apply different data series.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/20220/155848874411365_en-US.png)

-   Style series:

    Some widgets such as line charts and bar charts can render multiple data series. You can set the **Series** field on the **Style** tab page.

    This field is used to define an array of styles and cyclically render different data series. As shown in the following figure, two series are defined. The widget uses the styles that are specified in \['Series 1','Series 2'\] to render the s field for data in cycles.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/20220/155848874411366_en-US.png)

-   Note
    -   The **Series Name** field is set to the name of the specified style, and also used as the legend name of the corresponding chart. If Series Name is empty, the legend name is set to the value of the s field specified for the target data series.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/20220/155848874411367_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/20220/155848874411368_en-US.png)

    -   The style series are mapped to the data series in the order of the series listed in the style setting rather than their names.

        For example, the style series \[Series1, Series 2, Series 3\] can be mapped to the data series \[\{s1: series 1 style\}, \{s2: series 2 style\}, \{s3: series 3 style\}, \{s4: series 1 style\}, \{s5: series 2 style\}\].

        **Note:** The s1, s2, s3, s4, and s5 parameters are sequentially set to the values of the s field.

    -   If some styles such as red s2 and blue s1 are required, you can sort the data in the filter or data source after configuring the style series.

        For example, if the style series are set to \[red, blue\], you can sort the data in the order of \[\{"s":"2"\},\{"s":"1"\}\].

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/20220/155848874511412_en-US.png)


## Why does the widget not change rendering after the callback ID is changed? {#section_byf_2fd_bfb .section}

-   Test the callback ID of the widget on the edit page.

    Cause: The widget on the edit page cannot obtain the callback value returned by other widgets.

    Solution: Use the default value in the URL, and then test the widget on the edit page.

    Example: `xxxx/admin/screen/123456? value=123&name=12345`

-   Test the callback ID of the widget on the Preview or Publish page.

    On the Preview or Publish page of the dashboard, press F12 in Windows or press Option+Command+I in macOS to go to the Network tab page in the console, search `multiple`, and then check whether the widget has requested the Callback ID parameter.

    -   If the search result is empty, the widget has not requested the Callback ID parameter. You must check the callback configuration.
    -   If the search result is not empty, the widget has requested the Callback ID parameter. You must check whether the callback parameter in the request is correct, and whether **Status Code** 200 is returned.

        If the response is an error, you must check the connection to the data source.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/20220/155848874511369_en-US.png)

-   If you have used the **Ticker Board** widget and Status Code 200 is returned, but the widget does not change rendering, you must check whether **Data Correction** is selected in the widget configuration.

    If Data Correction is selected and the specified value is smaller than the current value, the widget does not change rendering.

    If your data is fluctuating and real-time data rendering is required, do not select Data Correction.


## How can I handle a timeout error when I configure a database as the data source? {#section_mkf_gfd_bfb .section}

1.  Make sure that you have completed the configuration as specified in [Database whitelist settings](../../../../reseller.en-US/User Guide/Manage data sources/Database whitelist settings.md#).
2.  If your data source is Alibaba Cloud RDS, you must configure the RDS whitelist as specified in [Configure RDS Whitelist](../../../../reseller.en-US/User Guide/Manage data sources/Database whitelist settings.md#), and make sure that you are using a VPC.<div data-spm-anchor-id="a2762.11472859.0.i97.67dc203byBKOZT"\>
    -   If you are using a VPC, when adding the data source, enable **VPC**, and enter the **VPC ID** and **Instance ID**.

        **Note:** You can obtain the VPC ID in the Alibaba Cloud VPC console and the instance ID in the Alibaba Cloud RDS console. Delete the front and end spaces of the ID before you enter it.

    -   If you are not using a VPC, contact the technical support.

## How can I handle a timeout error when a component requests data? {#section_edw_3fd_bfb .section}

-   Cause: The data query has timed out. The timeout value of requests sent to the database is set to 10s in DataV. If the data query time exceeds 10s, a timeout error occurs.

    Solution: This timeout value is specified on the server of DataV. You cannot modify this setting. We recommend that you optimize the corresponding SQL statement, or adjust the table structure to decrease the query time.

-   Cause: The widget data query consumes too much time, but the interval of requesting the widget auto update is less than the query time. Google Chrome supports a maximum of six HyperText Transfer Protocol \(HTTP\)-based requests to access the same domain at the same time. The subsequent requests will be pending, and Google Chrome will not be able to send them to the data center.

    Solution: We recommend that you adjust the interval of requesting the widget auto update, or optimize the corresponding SQL statement to decrease the query time.

    **Note:** Solution to long-time queries:

    -   Create an API that supports the DataV service for cross-origin data integration.
    -   Optimize the database query. For example, create related indexes based on common SQL conditions to accelerate the query.

## How can I write the SQL statement when the value of the Callback ID parameter is an array? {#section_apf_lfd_bfb .section}

-   Common SQL statement

    ```
     select * from tb where id in (:idList)
    ```

-   Stored procedure

    ```
    function(concat_ws(',', :idList))
    ```

    **Note:** The `idList` object is the array that you configured for the Callback ID parameter.


## How can I handle a DataV data proxy request disconnection? {#section_lnt_skz_gfb .section}

Follow the following steps to troubleshoot:

1.  Check if there is a **configuration error** message on the request interface.
    -   If a configuration error message appears, the disconnection is caused by a key and secret parsing error. Solutions:
        1.  You can search for time in any web browser search engine, and then check if the local time of your machine is the same as the standard time.
        2.  Check if the key and secret are filled with errors, such as extra spaces. We recommend that you create a new key and secret.
    -   If a configuration error does not appear, take the next step.
2.  Log on to the machine where you installed the data proxy to access `ip:9998/status` through a browser \(for example 128.23. \*\*. \*\*: 9998/status, 9998 is the default port for Data Proxy Service\), and then check if your Data Proxy Service starts properly.
    -   If your Data Proxy Service starts properly, take the next step.
    -   If your Data Proxy Service starts improperly, restart your Data Proxy Service.
3.  Check if the machine where you installed the data proxy is configured with an HTTPS certificate issued by a third party.
    -   If the machine is configured with an HTTPS certificate, take the next step.
    -   If the machine is not configured with an HTTPS certificate, modify the DataV page address protocol to http when accessing your the data proxy.
4.  Check if the machine where your data proxy is installed connects to your database.
    -   If the machine connects to your database, open a ticket on the DataV console, or contact Alibaba Cloud technical engineers directly.
    -   If the machine does not connect to your database, check if your data proxy configuration is correct.

