# FAQ {#concept_wps_xpt_q2b .concept}

## How do I configure multiple series? {#section_gvg_zpt_q2b .section}

-   In the data pane, if multiple s fields exist, values of the s fields indicate different series \(lines\).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832489580_en-US.png)

    **Note:** In the configuration pane, the style of the configuration items is rendered according to the data sequence. That is, if the data of series 2 is displayed first in a chart, all subsequent data of series 2 is rendered according to the configured style of series 1. You can customize the rendering effect by sorting the data in advance using a data filter.

    -   You can set the style of multiple series in the configuration pane.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832489581_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832489582_en-US.png)

    -   If the number of the actual series is greater than that in the configuration pane, the data in the configuration pane is rendered in a loop.

        As shown in the following figure, the style of series 3 is the same as that of series 1.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832489583_en-US.png)

        As shown in the following figure, data of series 2 is displayed first. Therefore, the data is rendered using the style of series 1 in the configuration pane.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832489584_en-US.png)

-   If the s field does not exist in the data pane, all the data belongs to the same series by default. That is, only the style of one series needs to be configured. \(If multiple series are set, only the configuration of the first series takes effect.\)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832489585_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832489586_en-US.png)


## What is the relationship between the series name in the configuration pane and the s field in the data pane? {#section_pxj_lqt_q2b .section}

The **series** option in the configuration pane determines the style of a series, while the **series name** determines the displayed text of a legend. You can customize the **series name** as needed. If the **series name** is empty, the system automatically searches for the value of the corresponding s field in the data pane. If the s field exists, the value of s is used as the series name. If this field does not exist, the series name is empty.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832499587_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832499588_en-US.png)

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17021/15580832499589_en-US.png)

