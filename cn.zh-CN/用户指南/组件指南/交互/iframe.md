# iframe {#concept_dc5_41r_gfb .concept}

iframe是基础交互组件的一种，支持自定义iframe链接，支持自定义iframe的显隐，适用于将网页嵌入大屏中进行显示。本文档为您介绍iframe各配置项的含义，帮助您快速准确地使用iframe组件。

## 样式 {#section_p4j_trq_gfb .section}

-   **基础属性**

    -   图表尺寸：通过修改宽度和高度，调整组件的大小。
    -   图表位置：通过修改横坐标和纵坐标，改变组件在布局中的位置。
    -   其他：调整组件的旋转角度和透明度。
-   **链接**：配置组件所显示页面的链接。

    **说明：** 建议声明http或者https协议，要注意https访问大屏时，iframe的链接若是http则无法访问。该链接的页面需要支持跨域。

-   **可关闭**：勾选后，在预览或发布页面，组件右上角会出现一个关闭按钮，单击此按钮可关闭该网页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21822/155807390812781_zh-CN.png)


## 数据 {#section_w1h_wqr_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21822/155807390813019_zh-CN.png)

-   url：配置组件所显示页面的链接，与**链接**配置项功能相同。如果同时配置，优先使用数据中的url。

## 交互 {#section_d3q_2sr_gfb .section}

勾选**启用**，开启组件交互功能。当iframe的链接发生变化时，会抛出您自定义的变量值。具体配置请参考[组件回调ID配置](../cn.zh-CN/最佳实践/配置数字翻牌器组件的回调ID.md#)。

