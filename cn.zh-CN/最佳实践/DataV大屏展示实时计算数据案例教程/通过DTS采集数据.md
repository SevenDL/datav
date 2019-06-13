# 通过DTS采集数据 {#concept_bmk_lpy_nfb .concept}

通过阿里数据传输中的数据同步（DTS），将RDS的数据实时传输至DataHub中。

1.  创建DataHub项目。
    1.  登录[DataHub控制台](https://datahub.console.aliyun.com/datahub)。
    2.  在**项目管理**中，选择区域，本案例选择**华东1**区。
    3.  单击**创建Project**，输入**名称**和**描述**，创建一个DataHub项目。本案例的项目名称为**datahub\_test\_datav**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039288513861_zh-CN.png)

2.  配置DTS数据同步作业。
    1.  登录[DTS控制台](https://dts.console.aliyun.com/)。
    2.  选择**数据同步** \> **创建同步作业**。
    3.  选择同步作业的基本配置。本案例的配置如下图所示，其中**源实例**选择**MySQL**，**源实例地域**选择**华东1**区，**目标实例**选择**DataHub**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039288513863_zh-CN.png)

    4.  返回**数据同步**页面，单击实例右侧的**配置同步链路**。
    5.  选择同步通道的源及目标实例，完成后单击**授权白名单并进入下一步**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039288513869_zh-CN.png)

        系统会自动为您创建同步账号，创建过程需要30秒左右，请耐心等待。当进度条显示为**100%**时，单击**下一步**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039288513870_zh-CN.png)

    6.  选择同步对象，单击**\>**图标按钮，此时需要同步的对象会出现在**已选择对象**列表中。本案例的同步对象为**datav\_test**数据库中的**mytable**表，如下图所示。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039288613871_zh-CN.png)

    7.  单击**预检查并启动**，预检查成功后，系统会自动跳转回数据同步页面。正常情况下，可以看到实例的状态为**初始化中**或**同步中**，且延时为0毫秒。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039288613872_zh-CN.png)

3.  查看数据采集结果。
    1.  回到[DataHub控制台](https://datahub.console.aliyun.com/datahub)，查看通过DTS创建的数据结构是否有缺失。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039288613873_zh-CN.png)

    2.  在RDS数据库中插入一条数据，单击**数据抽样**，查看增量数据同步结果。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039288713874_zh-CN.png)

        **说明：** 

        -   DataHub同步的是增量数据，您的数据库中必须插入、删除或更新一条或多条数据后，才会同步到DataHub中。本案例采用手动插入数据的方法，但在实际情况中，都是将用户的购买行为，通过程序的方式动态同步到数据库中的。
        -   进行数据抽样时，指定的时间必须在您插入数据之前。
        -   参考[创建 MySQL 到 MaxCompute 数据实时同步作业](https://help.aliyun.com/document_detail/44547.html)的同步原理章节，了解DataHub中各字段的含义。

