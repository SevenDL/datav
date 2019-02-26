# 添加 Table Store 数据源 {#concept_e42_c5h_wfb .concept}

[表格存储](https://www.aliyun.com/product/ots)（Table Store）是构建在阿里云飞天分布式系统之上的分布式 NoSQL 数据存储服务。

## 操作步骤 {#section_lnc_fgq_p2b .section}

1.  单击**我的数据** \> **添加数据**。
2.  单击**类型**下拉菜单，选择数据库类型为 **TableStore**。
3.  填写 Table Store 相关信息，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155114615632624_zh-CN.png)

    -   **名称**：数据源的显示名称，您可以自由命名。
    -   **AK ID**：拥有 Table Store 访问权限的账号的 AccessKey ID。
    -   **AK Secret**：拥有 Table Store 访问权限的账号的 AccessKey Secret。
    -   **外网**：Table Store 的[服务地址](https://help.aliyun.com/document_detail/52671.html)，需要根据访问的 Table Store 实例来填写。
    数据库信息填写完成后，系统会自动进行测试连接，验证能否正常连通。

4.  测试连接成功后，单击**确定**保存，完成数据源添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用 Table Store 数据源 {#section_jln_qgz_5fb .section}

1.  在 DataV 控制台上，单击**我的可视化**，选择您的项目，单击**编辑**，进入大屏编辑界面。
2.  单击选择某一组件，在数据面板中，选择**数据源类型**为 **TableStore**。
3.  单击**选择已有数据源**下拉菜单，选择配置完成的 Table Store 数据源 。
4.  单击**选择操作**下拉列表选择需要的操作，系统支持以下两种操作方式：
    -   getRow：对应 Table Store 的 GetRow API，详情请参考 [GetRow API 参考](https://help.aliyun.com/document_detail/27305.html)。
    -   getRange：对应 Table Store 的 GetRange API，详情请参考 [GetRange API 参考](https://help.aliyun.com/document_detail/27309.html)。
5.  在**选择操作**下的编辑框中输入查询语句，查询参数说明如下：
    -   查询参数必须为 JSON 对象。
    -   选择 getRow 操作时，需要根据指定的主键读取单行数据。

        参数格式：

        ```
        
        {
        "table_name": "test",
        "rows": {
        "id": 2
        },
        "columns": [
        "id",
        "test"
        ]
        }
        ```

        参数含义：

        -   table\_name：填写您需要查询的 Table 名。
        -   rows：填写行的过滤条件，将筛选出符合条件的行返回。如果您需要在 rows 里面添加 column 作为查询条件，那么所添加的 column 必须是建立过索引的。
        -   columns：填写需要返回的列名。
    -   getRange操作用于读取指定主键范围内的数据，参数格式：

        ```
        
        {
        "table_name": "test",
        "direction": "FORWARD",
        "columns": [
        "id",
        "test"
        ],
        "range": {
        "limit": 4,
        "start": {
        "id": "InfMin"
        },
        "end": {
        "id": 3
        }
        }
        }
        ```

        参数含义：

        -   table\_name：填写您需要查询的 Table 名。
        -   direction：查询的顺序。
        -   columns：填写需要返回的列名。
        -   limit：读取最多返回的行数。
        -   start：指定读取时的起始列，返回的结果中包含当前起始列，所列出的 column 必须是已经建立索引的列。
        -   end：指定读取时的结束列，返回的结果中不包含当前结束列，所列出的 column 必须是已经建立索引的列。
        **说明：** start 和 end 参数里可以使用 InfMin、InfMax 表示最小值和最大值 。

6.  单击**查看数据响应结果**，数据响应成功后即可看到效果。

## 调用示例 {#section_vrs_kpt_vfb .section}

1.  准备 Table Store 数据。

     您需要先在[Table Store控制台](https://ots.console.aliyun.com/)[创建实例](https://help.aliyun.com/document_detail/55211.html)并[存储数据](https://help.aliyun.com/document_detail/55220.html)。如下图建立了一个实例名为 test1948 的实例，里面有 3 行数据，每行数据有两个列：id\(主键, integer\)， test\(string\)。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155114615632810_zh-CN.png)

2.  配置数据源。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155114615632811_zh-CN.png)

3.  查询参数。

    -   getRow：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155114615632812_zh-CN.png)

        数据响应结果如下图所示：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155114615632813_zh-CN.png)

    -   getRange：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155114615732814_zh-CN.png)

        数据响应结果如下图所示：

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64591/155114615732815_zh-CN.png)

    **说明：** 在查询 getRange 参数的时候，过滤条件 start 为 id：InfMin，end 为 id：3，最后查出来 id 为 1 和 2 两行记录，因为 getRange 并不包含 end 的行，即不包含 id 为 3 的行。


