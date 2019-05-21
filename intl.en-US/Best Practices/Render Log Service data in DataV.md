# Render Log Service data in DataV {#concept_x5d_rcm_q2b .concept}

The following sections describe how to configure DataV to render data from Log Service.

The following sections describe how to:

-   Create and configure Log Service to work with DataV \(set indexes\).
-   Create a sample dashboard.
-   Share the dashboard publicly.

## Prerequisites {#section_rp2_vcm_q2b .section}

-   You must have completed [Configure Log4JAppender with Kubernetes and Log Service](../../../../reseller.en-US/User Guide/Kubernetes cluster/Log management/Configure Log4jAppender for Kubernetes and Log Service.md#)and the service is currently running.
-   You must have purchased DataV Enterprise Edition.

## Configure Log Service {#section_av1_xcm_q2b .section}

1.  Visit the Logstore List page within your project.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084218038_en-US.png)

2.  Click **Search** next to the name of your project. The following page is displayed:

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084218039_en-US.png)

3.  Create indices for all required fields. The following example creates an index for each item. Click**Index Attributes** from the upper menu of the page and click **Modify**.
4.  Verify the data from the Search & Analysis page:

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084218041_en-US.png)

5.  Once the data has been imported properly, switch to **Graph** view \(in the following graph, the axis is ‘time’\):

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084218042_en-US.png)


## Configure DataV {#section_vq4_pgm_q2b .section}

1.  1. Visit the DataV product page to create your first project.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084218043_en-US.png)

2.  Click **Create Project**, select a blank template, and click **Create**.
3.  Add a widget to the dashboard.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084218045_en-US.png)

    The widget displays some sample static dataset.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084218046_en-US.png)

4.  Click the widget and, select the Log Service \(SLS\) from Data Source Type from the **Data** tab on the right side.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084228047_en-US.png)

5.  Click **Create** in the Select Data Source. The New data dialog is displayed, fill in the relevant information, and click **OK**.

    **Note:** Make sure you add `http://` or `https://` in the Endpoint field.

6.  Once completed, select the newly created Source. The following example uses a simple example query:

    ```
    {
    "projectName": "k8s-logs",
    "logStoreName": "k8s-logstore",
    "topic": "",
    "from": "1518883200",
    "to": "1518969600",
    "query": "* | select count(1) as pv, date_format(from_unixtime(__time__ - __time__%3600) ,'%Y/%m/%d %H:%i:%s') as time group by time order by time limit 1000" ,
    "line": 100,
    "offset": 0
    }
    ```

    **Note:** from and to are the timestamps you can use to examine raw data in the Search console.

7.  Preview the data by clicking **View Data Response** button at the lower-side of the window. The following response result window is displayed:

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084228049_en-US.png)

8.  Click **Select Filter** and apply the following filter to make sure the `pv` is an integer, and click **OK**.

    ```
    return Object.keys(data).map((key) => {
     let d= data[key];
     d["pv"] = parseInt(d["pv"]);
     return d;
    }
    )
    ```

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084228050_en-US.png)

9.  Set the axes and verify the settings are set correctly.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084228052_en-US.png)

10. Click **Preview**.

    You can see that `x` and `y` use the correct data type, and `pv` is an integer.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084228054_en-US.png)

11. To share this dashboard publicly, click **Publish** in the upper-right corner of the page.

    An example of a completed and published DataV dashboard, using a dataset from a Log Service data, is as follows:

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084228056_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16936/15584084228057_en-US.png)


## Conclusion {#section_q3s_nhm_q2b .section}

You have successfully configured DataV and Log Service together on Alibaba Cloud and used Log Service to perform real-time monitoring by means of a custom dashboard.

## References {#section_adn_4hm_q2b .section}

For more information on Log Service and containers, see

-   [Log Service](https://partners-intl.console.aliyun.com/#/log-service)
-   [Container Service](https://partners-intl.console.aliyun.com/#/container-service)

