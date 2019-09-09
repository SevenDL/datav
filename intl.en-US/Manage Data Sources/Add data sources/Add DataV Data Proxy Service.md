# Add DataV Data Proxy Service {#concept_ltx_glp_p2b .concept}

DataV Data Proxy Service is a database connection tool that provides highly secure connections. If you are concerned about data privacy and security issues, you can use DataV Data Proxy Service. If your data cannot be accessed through the Internet, or you are not using Alibaba Cloud database services, you must expose the Internet IP address of your database to establish the connection.

## **Procedure** {#section_eng_2hr_p2b .section}

1.  Use the HTTP protocol to enter the [DataV console](http://partners-intl.console.aliyun.com/#/datav), and select **Data Sources** \> **Add Source**.
2.  Select **DataV Data Proxy Service** from the **Type** drop-down list.

    **Note:** 

    -   This service SDK only provides HTTP services. If you need HTTPS services, you must apply for an HTTPS certificate recognized by Google Chrome.
    -   We recommend you enable HTTP services until the HTTPS certificate is applied.
3.  Enter the database information.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16538/15679989117911_en-US.png)

    -   **Name**: Displays the name of the data source.
    -   **Host**: The IP address of your server. If you are using an ECS server, you should configure it as the public IP of the ECS server.
    -   **Port**: The Port is automatically generated after the code package is downloaded and installed.
    -   **Key**: The Key is automatically generated after the code package is downloaded and installed.
    -   **Secret**: The Secret is automatically generated after the code package is downloaded and installed.

        To obtain a Key and a Secret, see [Introduction to the DataV Proxy service](reseller.en-US/Advanced Skills/Introduction to the DataV Proxy service.md#).

    -   **Database**: The name of the currently selected database.
    If all the parameters are configured, the system will test the data source connection automatically.

4.  Click **OK** when the connection is verified.

