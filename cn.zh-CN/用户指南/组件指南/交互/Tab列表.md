# Tab列表 {#concept_wp5_zqs_gfb .concept}

使用Tab列表组件，配置您大屏项目中需要的Tab列表。您也可以通过组件的交互功能，为您的Tab列表添加交互事件。

## 样式 {#section_p4j_trq_gfb .section}

-   **基础属性**

    -   图表尺寸：通过修改宽度和高度，调整组件的大小。
    -   图表位置：通过修改横坐标和纵坐标，改变组件在布局中的位置。
    -   其他：调整组件的旋转角度和透明度。
-   **字体**：单击下拉箭头，选择组件的字体。
-   **背景色**：参考[颜色选择器说明](cn.zh-CN/用户指南/管理组件/设置组件样式/配置项说明.md#section_kdw_vj4_t2b)，设置组件的背景颜色。
-   **行数**：手动输入数值或单击**+**或**-**号，调整Tab列表的行数。
-   **列数**：手动输入数值或单击**+**或**-**号，调整Tab列表的列数。
-   **选择类型**：包括**单选**和**多选**，单击下拉箭头进行切换。
-   **初始化值**：请填入期望初始化选中的标签ID，此ID与数据中id字段的值要一一对应。当组件的**选择类型**为**单选**时，该选项只能包括一个值。当组件的**选择类型**为**多选**时，该选项可以包含多个值，多个值之间用英文逗号隔开。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/154174371812905_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/154174371812906_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/154174371812909_zh-CN.png)

-   **全部按钮**：只有当组件的**选择类型**为**多选**时，此选项才会显示。勾选此选项，Tab列表中会出现**全部**的Tab选项卡。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/154174371812911_zh-CN.png)

-   **初始化全选**：只有当组件的**选择类型**为**多选**时，此选项才会显示。勾选此选项，组件初始化时会选中所有的Tab选项卡，且**初始化值**配置项隐藏。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/154174371912914_zh-CN.png)

-   **标签默认配置**

    -   **字号**：手动输入数值或者拖动滑块，调整组件标签的字号大小。
    -   **字体颜色**：参考[颜色选择器说明](cn.zh-CN/用户指南/管理组件/设置组件样式/配置项说明.md#section_kdw_vj4_t2b)，设置组件标签的字体颜色。
    -   **字体粗细**：单击下拉箭头，选择组件标签的字体粗细。
    -   **背景颜色**：参考[颜色选择器说明](cn.zh-CN/用户指南/管理组件/设置组件样式/配置项说明.md#section_kdw_vj4_t2b)，设置Tab选项卡的背景颜色。
    -   **圆角半径**：手动输入数值或者拖动滑块，调整Tab选项卡的圆角半径，值越大，边角越圆。默认为0，即为长方形。
    -   **悬浮背景色**：参考[颜色选择器说明](cn.zh-CN/用户指南/管理组件/设置组件样式/配置项说明.md#section_kdw_vj4_t2b)，设置Tab选项卡的悬浮背景色。只有在预览或者发布页面，才能看到配置效果。
    -   **选中文字色**：参考[颜色选择器说明](cn.zh-CN/用户指南/管理组件/设置组件样式/配置项说明.md#section_kdw_vj4_t2b)，设置Tab选项卡被选中时的文字的颜色。
    -   **选中背景色**：参考[颜色选择器说明](cn.zh-CN/用户指南/管理组件/设置组件样式/配置项说明.md#section_kdw_vj4_t2b)，设置Tab选项卡被选中时的背景颜色。
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/154174371912929_zh-CN.png)

-   **交互**：设置组件的回调ID。

## 数据 {#section_llq_l3t_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/154174371912930_zh-CN.png)

-   id：Tab选项卡的标签ID，与样式面板中的配置的初始化值一一对应。
-   content：Tab选项卡的标签显示的名称。

## 交互 {#section_d3q_2sr_gfb .section}

勾选**启用**，开启组件交互功能。具体配置请参考[组件回调ID配置](../cn.zh-CN/最佳实践/配置数字翻牌器组件的回调ID.md#)。

