# Overview {#concept_ldr_4gp_p2b .concept}

Log on to the [DataV console](https://partners-intl.console.aliyun.com/#/datav), and select **Data Sources** in the left-side navigation pane to manage data sources.

DataV supports access to the following data sources:

-   Database
-   CSV file and static JSON
-   API
-   Others

## Databases {#section_lgm_lkp_p2b .section}

DataV supports the following types of databases:

-   [RDS for MySQL](reseller.en-US/Manage Data Sources/Add data sources/Add RDS for MySQL.md#)
-   [RDS for PostgreSQL](reseller.en-US/Manage Data Sources/Add data sources/Add RDS for PostgreSQL.md#)
-   [RDS for SQLServer](reseller.en-US/Manage Data Sources/Add data sources/Add RDS for SQLServer.md#)
-   [Table Store](reseller.en-US/Manage Data Sources/Add data sources/Add a Table Store data source.md#)
-   [Oracle](reseller.en-US/Manage Data Sources/Add data sources/Add Oracle.md#)
-   [MySQL-compatible database](reseller.en-US/Manage Data Sources/Add data sources/Add compatible MySQL.md#)

If you are not using Alibaba Cloud and want to connect DataV to your own database, you must use the Internet IP address of the database to establish connection. We currently do not support IP whitelists. We recommend using an Alibaba Cloud database connection agent tool provide if you have any security concerns.

## CSV and Static JSON {#section_dhc_bbq_p2b .section}

DataV supports the following types of static data:

-   [CSV file](reseller.en-US/Manage Data Sources/Add data sources/Add CSV files.md#)
-   [Static JSON](reseller.en-US/Manage Data Sources/Add data sources/Add static JSON.md#)

DataV currently does not support reading large data files from other file storage you may have.

## APIs {#section_vts_lbq_p2b .section}

DataV supports the following types of APIs as data sources:

-   POP API
-   [Alibaba Cloud API Gateway](https://partners-intl.console.aliyun.com/#/apigateway)

You can directly copy and paste an API address into the **Data configuration** panel. If your API has an authentication process, you must encapsulate the API in [Alibaba Cloud API Gateway](https://partners-intl.console.aliyun.com/#/apigateway), and access it through configurations of Alibaba Cloud API gateway.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16532/15679987297800_en-US.png)

## Others {#section_myj_l2q_p2b .section}

DataV data proxy service provides an open source database proxy service for you to deploy on your ECS. The data proxy service reduces the risks that may arise from the exposure of the Internet IP address of your database.

For more information about the deployment and installation of DataV data proxy services, see [Introduction to the DataV Proxy service](reseller.en-US/Advanced Skills/Introduction to the DataV Proxy service.md#).

