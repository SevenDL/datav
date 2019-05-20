# Add RDS for MySQL {#concept_xdt_blp_p2b .concept}

## RDS for MySQL for intranet {#section_t1g_hmq_p2b .section}

-   **Procedure**
    1.  Log on to the [DataV console](https://partners-intl.console.aliyun.com/#/datav) and select **Data Sources** \> **Add Source**.
    2.  Select RDS for MySQL from the **Type**drop-down list.
    3.  Click the secondary drop-down list and select **Intranet**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15583487557824_en-US.png)

    4.  Enter the database information in the New Data Source dialog box.

        Database type connections for Alibaba Cloud intranet IP connections of **East China 1**, **East China 2**, **North China 2** and Internet IP connections are currently supported. IP whitelists are not supported.

        If you want to create a new database, see [Create a Database](https://partners-intl.console.aliyun.com/#/datav).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15583487557826_en-US.png)

        -   **Name**: Displays the name of the data source.
        -   **Host**: The URL of your database. This cannot be the URL of your official website or your local IP. It must be a URL that the DataV server can use to access your database through the Internet or intranet from the Alibaba Cloud data.
        -   **Username**: The username that you use to log on to your database.
        -   **Password**: The password that you use to authenticate your database account.
        -   **Port**: The IP address port number of your database.
        -   **Database**: The name of the currently selected database.
        If all the parameters are configured, the system will test the data source connection automatically.

    5.  Click **OK** when the connection test is verified.

        When a data source is added, it will be displayed in the data source list.


## RDS for MySQL \(Internet\) {#section_hq4_hqq_p2b .section}

-   **Procedure**
    1.  Log on to the [DataV console](https://partners-intl.console.aliyun.com/#/datav) and select **Data Sources** \> **Add Source**.
    2.  Select RDS for MySQL from the Type drop-down list.
    3.  Click the secondary drop-down list and select **Internet**.

        If you want to set an Internet address, see [Set Internet and intranet Address](https://partners-intl.console.aliyun.com/#/datav).

    4.  Enter the database information in the New Data Source dialog box.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16534/15583487557829_en-US.png)

        -   **Name**: Displays the name of the data source.
        -   **Host**: The URL of your database. This cannot be the URL of your official website or your local IP. It must be a URL that the DataV server can use to access your database through the Internet or intranet from the Alibaba Cloud data.
        -   **Username**: The username that you use to log on to your database.
        -   **Password**: The password that you use to authenticate your database account.
        -   **Port**: The IP address port number of your database.
        -   **Database**: The name of the currently selected database.
        If all the parameters are configured, the system will test the data source connection automatically.

    5.  Click **OK** when the connection test is verified.

        When a data source is added, it will be displayed in the data source list.


