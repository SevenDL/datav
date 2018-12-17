# 添加日志服务SLS数据源 {#concept_z2h_vgt_cgb .concept}

[日志服务](https://www.aliyun.com/product/sls)（Log Service，简称LOG/原SLS）是针对实时数据的一站式服务。

## 操作步骤 {#section_lnc_fgq_p2b .section}

1.  单击**我的数据** \> **添加数据**。
2.  单击**类型**下拉菜单，选择数据库类型为**简单日志服务SLS**。
3.  填写SLS相关信息，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79886/154503960834422_zh-CN.png)

    -   **名称**：数据源的显示名称，您可以自由命名。
    -   **AppKey**：拥有目标SLS访问权限的账号的 AccessKey ID。
    -   **AppSecret**：拥有目标SLS访问权限的账号的 AccessKey Secret。
    -   **EndPoint**：填写SLS服务的EndPoint。请参考[日志服务入口文档](https://help.aliyun.com/document_detail/29008.html)，根据您SLS服务的网络类型和所在区域进行填写。

        例如VPC网络下，上海区域的**EndPoint**填写为**https://cn-shanghai-intranet.log.aliyuncs.com**。

    数据库信息填写完成后，系统会自动进行测试连接，验证能否正常连通。

4.  测试连接成功后，单击**确定**保存，完成数据源添加。

    新添加的数据源会自动显示在数据源列表中。


## 配置日志服务 {#section_blw_bh5_cgb .section}

请参考[日志服务](https://help.aliyun.com/product/28958.html)官方帮助文档，开通、配置并使用日志服务。

## 使用SLS日志服务数据源 {#section_jln_qgz_5fb .section}

1.  在DataV控制台上，单击**我的可视化**，选择您的项目，单击**编辑**，进入大屏编辑界面。
2.  单击选择某一组件，在数据面板中，选择**数据源类型**为**日志服务**。
3.  单击**选择已有数据源**下拉菜单，选择配置完成的日志服务数据源 。
4.  在查询编辑框中输入查询参数，查询参数支持以下两种格式：
    -   JSON 对象，可填写的查询参数为：

        ```
        {
        "projectName": "test",
        "logStoreName": "access-log",
        "topic": "test",
        "from": 1509897600,
        "to": 1509984000,
        "query": "" ,
        "line": 100,
        "offset": 0
        }
        ```

    -    query 参数查询语法：[https://help.aliyun.com/document\_detail/29060.html](https://help.aliyun.com/document_detail/29060.html)。
5.  单击**查看数据响应结果**，数据响应成功后即可看到效果。

