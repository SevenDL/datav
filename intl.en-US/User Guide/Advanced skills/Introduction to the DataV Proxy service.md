# Introduction to the DataV Proxy service {#concept_wws_yvg_chb .concept}

This topic describes how to start the DataV Proxy service and what are the features of this service. With the DataV Proxy service, you can configure data queries without the need for opening a database or building an API. The DataV Proxy service sends encrypted SQL strings and the ID of a database to an application. Then the application connects to the database, obtains the query results, and returns the results to DataV.

## Startup {#section_qmk_trb_dhb .section}

To start the DataV Proxy service, follow these steps:

-   For Windows:
    1.  Click [Download DataV Proxy](https://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_proxy.zip) to download the installation package.
    2.  Decompress the installation package.
    3.  Double-click the datav\_proxy\_wins.exe file.
-   For Linux and Mac OS:
    1.  Run the following command to download the DataV Proxy application:

        ``` {#codeblock_uhu_xre_fuj}
        wget https://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_proxy.zip                        
        ```

    2.  Decompress the installation package and find the directory where the DataV Proxy service is located.
    3.  Run the following command to start the DataV Proxy service:

        ``` {#codeblock_bak_dsx_m4a}
        chmod 777 ./*
        sh exec.sh start
        ```

        **Note:** By default, the DataV Proxy service is started on port 8001.

        You can run the sh exec.sh start -p \[port number\] command to start the DataV Proxy service. In this command, you can set the port number as needed \(for example, sh exec.sh start -p 8080\).

        You can also run the sh exec.sh stop command to stop the DataV Proxy service.


After the DataV Proxy service is started, you can paste `http://domain name:port` into a browser to access the service.

-   `domain name`: The Internet IP address of the server to install the DataV Proxy service.
-   `Port`: The port on which the DataV Proxy service is started.

**Note:** You must first register the DataV Proxy service before you can use it.

## Features {#section_ncg_mtb_dhb .section}

-   Customize the data source

    You can configure the basic information about a database, such as the data source. This information is used when you configure the database as a data source for DataV. After the basic information is configured, you can click **link** and **SQL** to test the reliability of the data source.

    To configure a data source, follow these steps:

    1.  In the left-side navigation pane, click **Data Source**, select the target data source, and click **Add**.

        ![Add a data source](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156195022340925_en-US.png)

    2.  In the displayed dialog box, enter basic information about the data source.

        ![Enter basic data source information](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156195022340926_en-US.png)

    3.  Test the data source.

        Click **link** to test the connectivity of the database.

        Click **SQL** and enter a SQL statement to test whether data in the database meets the requirements.

        ![Test the data source](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156195022340927_en-US.png)

-   Query logs

    You can query logs by specifying the number of columns that contain keywords.

    ![Query logs](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156195022440928_en-US.png)

    **Note:** You can only view logs on Windows and cannot query logs by specifying the number of columns that contain keywords.

-   Automatically generate keys and secrets

    You can click **create key/secret** to generate a pair of key and secret that can be used to configure DataV data sources. When you create a new pair, your existing key and secret automatically expire.

    ![Create a key and secret](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/138868/156195022440929_en-US.png)

    **Note:** By default, no key and secret are available. You need to click **create key/secret** to generate a pair of key and secret for subsequent use.


