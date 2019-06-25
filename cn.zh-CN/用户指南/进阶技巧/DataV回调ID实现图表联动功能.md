# DataV回调ID实现图表联动功能 {#concept_pbb_2vk_q2b .concept}

本文档为您介绍在DataV控制台中单击某一个图表，需要另外一个图表的数据也会有相应变化时，可以通过配置组件的回调ID，来实现图表联动的方法。

## 什么是回调ID {#section_wcx_b2t_cgb .section}

回调ID可以理解为参数变量，用于控制组件之间参数的传递，从而达到交互的目的。比如下图中的地图组件，单击地图上的某一个点显示这个点的详细信息，就是通过配置地图子组件的[回调ID](cn.zh-CN/用户指南/管理组件/配置组件交互.md#)来实现的。

![地图组件回调ID](images/8532_zh-CN.gif)

## 如何设置回调ID {#section_ef1_p35_q2b .section}

1.  选择某个组件，单击编辑器画布右侧的**交互**页签。
2.  勾选数字变化响应事件右侧的**启用**。

    ![启用回调ID](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16584/15614529498533_zh-CN.png)

3.  修改**绑定到变量**中的变量名称，如下图所示，将lng修改为 x，lat修改为y。

    ![修改变量名称](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16584/156145294934249_zh-CN.png)

    配置完成后，其他组件就可以使用x和y来取得对应的参数值了。


## 如何使用回调ID {#section_i5q_535_q2b .section}

在SQL或API数据源中，通过`:变量名`（如 `:x`）使用您已经配置的变量。

-   SQL：

    ``` {#codeblock_x8o_qqe_709}
    select :x as value
    select A from table where lng = :x
    ```

-   API：

    ``` {#codeblock_ap7_ccz_atb}
    http://api.test?lng=:x&lat=:y
    ```


**说明：** 

-   如果您的**数据源类型**为**静态数据**或者**CSV文件**，则不支持回调ID的使用。
-   对于API数据源，系统会直接为同名的变量参数赋值。
-   DataV提供了回调参数自动补全功能。在配置数据源时，只要键入`:`，编辑器将提示当前屏幕下所有配置过的变量名称。您可以使用上下键选择某个变量名称，完成后按**Enter**键确定。当屏幕中有大量交互组件的时候，这个功能可以帮助您方便快速地使用回调ID。

    ![回调参数自动补全功能](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16584/156145295034251_zh-CN.png)


