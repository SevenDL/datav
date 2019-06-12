# 配置数字翻牌器组件的回调ID {#concept_m2n_fy3_52b .concept}

在DataV中，回调ID是指某个组件在响应用户操作或者自动触发更新时向别的组件传递的参数，这个参数可以在别的组件中作为数据查询时的动态变量。本文档以**数字翻牌器**组件为例，为您介绍回调ID的使用方法。

## 操作步骤 {#section_vqv_1kk_52b .section}

1.  选择数字翻牌器组件，单击编辑器右侧的**交互**页签。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15603221769296_zh-CN.png)

    **说明：** 最新版本的DataV提供了一个回调ID的独立编辑区块，方便您清晰快速地使用回调ID功能。

2.  勾选**数字变化响应事件**右侧的**启用**。
3.  修改**绑定到变量**中的变量名称，如下图所示，将value修改为income。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15603221769297_zh-CN.png)

    **说明：** 

    -   变量名称修改为income后，在需要响应回调ID的组件中就可以使用income来取得这个参数值。
    -   使用这一特性，您可以给不同的组件设置不一样的变量名称，达到区分使用不同参数的目的。
4.  单击需要响应回调ID的组件，在数据配置页面的数据源编辑框中，通过`:变量名`（如`:income`）使用您已经配置的变量。

    -   SQL:

        ``` {#codeblock_2hm_xuc_56s}
        select :income as value
        select A from table where income = :income
        ```

    -   API:

        ``` {#codeblock_kwj_mbi_spi}
        http://api.test?income=:income&id=:myid
        ```

    **说明：** 

    -   如果您的**数据源类型**为**静态数据**或者**CSV 文件**，则不支持回调ID的使用。
    -   DataV提供了回调参数自动补全功能。在配置数据源时，只要键入`:`，编辑器将提示当前屏幕下所有已经配置过的变量名称。您可以使用上下键选择某个变量名称，完成后按 Enter 键确定。当屏幕中有大量交互组件的时候，这个功能可以帮助您方便快速地使用回调ID。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15603221769300_zh-CN.png)


## 高级功能 {#section_id3_bcz_q2b .section}

-   **设置自定义字段**

    1.  单击数字翻牌器组件的数据页签。
    2.  在数据源中设置一个id字段，值为123。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15603221769298_zh-CN.png)

    3.  单击交互页签，返回组件的交互配置页面。
    4.  单击**新建一个字段**。
    5.  在**字段**列输入id，在**绑定到变量**列输入您要设置的变量名称。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17483/15603221779299_zh-CN.png)

        **说明：** 只有同时填写了**字段**和**绑定到变量**后，这个变量才会生效。

-   **设置回调ID的默认值**

    您可以通过在URL中设置请求参数的形式来设置回调ID的默认值，示例如下。

    ``` {#codeblock_tn8_6iw_gso}
    http://datav.aliyun.com/screen/000000?myid=123
    ```

     `000000`表示屏幕id。

    通过这个URL访问大屏时，在页面打开的时候，回调ID的myid的值已经设置为123了。

    多个回调ID之间使用“&”符号连接，如下的示例中同时设置了回调ID的myid和income的默认值。

    ``` {#codeblock_nli_iyp_wq9}
    http://datav.aliyun.com/screen/000000?myid=123&income=1000
    ```

     `000000`表示屏幕id。


