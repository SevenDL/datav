# iframe {#concept_dc5_41r_gfb .concept}

使用iframe组件，可以在您的大屏项目中添加一个或多个iframe模块，用于显示不同的链接页面。

## 样式 {#section_p4j_trq_gfb .section}

-   **基础属性**

    -   图表尺寸：通过修改宽度和高度，调整组件的大小。
    -   图表位置：通过修改横坐标和纵坐标，改变组件在布局中的位置。
    -   其他：调整组件的旋转角度和透明度。
-   **链接**：配置组件所显示页面的链接。

    **说明：** 建议声明http或者https协议，要注意https访问大屏时，iframe的链接若是http则无法访问。该链接的页面需要支持跨域。

-   **可关闭**：勾选后，在预览或发布页面，组件右上角会出现一个关闭按钮，单击此按钮可关闭该网页。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21822/154174375912781_zh-CN.png)


## 数据 {#section_w1h_wqr_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21822/154174375913019_zh-CN.png)

url：配置组件所显示页面的链接，与样式中的**链接**功能相同。如果同时配置，则以url中的链接为准。

## 交互 {#section_d3q_2sr_gfb .section}

勾选**启用**，开启组件交互功能。具体配置请参考[组件回调ID配置](../cn.zh-CN/最佳实践/配置数字翻牌器组件的回调ID.md#)。

