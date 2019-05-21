# Overview {#concept_prb_n1r_52b .concept}

This topic describes how to create a project in DataV to view air quality changes before and after the Spring Festival.

## Procedure {#section_pys_ttj_p2b .section}

1.  Make preparations.
    1.  [Obtain data](reseller.en-US/Best Practices/Use DataV to view air quality changes before and after the Spring Festival/Preparations/Obtain data.md#)
    2.  [Process data](reseller.en-US/Best Practices/Use DataV to view air quality changes before and after the Spring Festival/Preparations/Process data.md#)
    3.  [Process the APIs](reseller.en-US/Best Practices/Use DataV to view air quality changes before and after the Spring Festival/Preparations/Process the APIs.md#)
2.  Create a project.
    1.  [Create a project](reseller.en-US/Best Practices/Use DataV to view air quality changes before and after the Spring Festival/Create a project/Create a project.md#)
    2.  [Add widgets](reseller.en-US/Best Practices/Use DataV to view air quality changes before and after the Spring Festival/Create a project/Add widgets.md#)
    3.  [Add data](reseller.en-US/Best Practices/Use DataV to view air quality changes before and after the Spring Festival/Create a project/Add data.md#)
3.  Publish the project.

    For more information, see [Publish a project](../../../../reseller.en-US/User Guide/Manage projects/Publish a project.md#).


## Description { .section}

You need to use the following feature or widgets when creating a project:

-   [Spatial interpolation](#)
-   [Isosurface layer](#)
-   [Timeline](#)

**Spatial interpolation**

Spatial interpolation is generally used to convert scattered data into consecutive data on a curve to compare the data with data in other distribution modes.

That is, the data obtained from existing monitoring sites can be used to estimate data of other locations. Then, colors are mapped according to the value range and an isothermal map is generated.

By creating an isothermal map using DataV, you will start the process of spatial interpolation, in which scattered data obtained from monitoring sites is used to create consecutive data on a curve.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17649/155842035647657_en-US.png)

**Isosurface layer**

DataV provides an isosurface layer map widget featuring lightweight analysis, which can help you create a grid area map using data of known vector points. You can use this widget to create a real-time air quality map, as shown in the following figure.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17649/15584203569377_en-US.png)

**Timeline**

The timeline widget is necessary to display air quality changes during a period of time.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17649/15584203569378_en-US.png)

This widget supports callback IDs, which can be used to connect this widget to other widgets. Data of connected widgets will be automatically updated when the time on the timeline changes.

If a correct callback ID is set, the system will trigger a data request when time changes and automatically adds the callback ID and the value of the callback ID to the parameter list of the corresponding APIs of other widgets.

-   IP address of the initial API: http://127.0.0.1:8888/aqi
-   IP address of the API after callback is triggered: http://127.0.0.1:8888/aqi?date=2017012722

The callback ID is `date,2017012722`.

The callback ID supports SQL statements. To use the callback ID, you need to use a colon \(`:`\) and the callback ID name in your SQL statements.

-   Initial SQL statement: `select :date as value;`
-   SQL statement after callback is triggered: `select '2017022722' as value;`

