# 通过DataV展示数据 {#concept_cyk_npy_nfb .concept}

通过DataV的SQL语句功能，处理数据，并将结果展示在大屏上。

1.  添加DataV数据源。
    1.  参考[配置数据库白名单](../../../../cn.zh-CN/用户指南/管理数据源/配置数据库白名单.md#)，在RDS控制台中配置数据库白名单。
    2.  登录[Datav控制台](https://datav.aliyun.com/)。
    3.  选择**我的数据** \> **添加数据**。
    4.  填写RDS实例的相关信息，单击**确定**。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039292713910_zh-CN.png)

        **说明：** 

        -   您可以在RDS实例的**基本信息**页面，获取以上信息。
        -   如果您的网络类型为**内网**，则对应的**域名**为RDS MySQL实例的内网地址。
        -   如果您的网络类型为**外网**，则对应的**域名**为RDS MySQL实例的外网地址。
2.  创建大屏项目。
    1.  选择**我的可视化** \> **新建可视化**。
    2.  选择一个模板，单击**创建**。本案例以全球贸易模板为例。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039292713911_zh-CN.png)

3.  配置数据源。
    1.  选择一个组件，单击控制台右侧的**数据**页签。本案例以**单值百分比饼图**组件为例。
    2.  选择**数据源类型**为**数据库**，**已有数据源**为第一步中创建的数据源。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039292813912_zh-CN.png)

    3.  在SQL输入部分输入如下SQL语句。

        ``` {#codeblock_dnz_8ag_b6z}
        SELECT count(*)/100 as value FROM target_table where dts_operation_flag='I'
        ```

        结果如下：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039292813982_zh-CN.png)

    4.  在源数据表（mytable）中插入三行数据，验证数据同步结果。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039292813983_zh-CN.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039292913984_zh-CN.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23955/156039292913985_zh-CN.png)

        可以看到，在源表中插入三条数据后，销售目标达成率由原来的2%变成了5%。


