# 配置DataV数据源 {#task_arn_mxh_ffb .task}

1.  登录[Datav控制台](https://datav.aliyun.com/)。
2.  选择**我的数据** \> **添加数据**。
3.  填写您已经创建完成的数据库的相关信息，单击**确定**。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21749/155850854112646_zh-CN.png)

 

    **说明：** 

    -   进入RDS控制台，单击RDS for MySQL实例链接，进入实例的**基本信息**页面，获取以上信息。
    -   如果您的网络类型为**内网**，则对应的**域名**为RDS for MySQL实例的内网地址。
    -   如果您的网络类型为**外网**，则对应的**域名**为RDS for MySQL实例的外网地址。
4.  单击**我的可视化** \> **新建可视化**，选择**云资源监控**模板，单击**创建**。
5.  输入**数据大屏名称**，单击**创建**。
6.  配置组件样式。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21749/155850854112667_zh-CN.png)

 
    1.  选择**资源消耗最大任务**下的轮播列表组件，单击画布右侧的**样式**图标按钮（![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21749/155850854114282_zh-CN.png)）。
    2.  在样式配置页面，单击**自定义列**。
    3.  单击**标签1**，设置**列字段名**为**c1**，**列显示名**为**content**。
    4.  单击**标签2**，设置**列字段名**为**c2**，**列显示名**为**age**。
7.  配置组件数据。 

    1.  单击画布右侧的**数据**图标按钮（![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21749/155850854114283_zh-CN.png)），进入数据设置页面。
    2.  选择**数据源类型**为**数据库**，**已有数据源**为您前面步骤中创建的数据源，如下图所示。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21749/155850854112650_zh-CN.png)


    3.  在SQL输入区域输入以下SQL语句。 

        ```
        SELECT c1,c2 FROM mytable
        ```

    4.  单击**查看数据响应结果**，查看数据是否配置成功。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21749/155850854112668_zh-CN.png)


    最终组件显示效果如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21749/155850854112669_zh-CN.png)


