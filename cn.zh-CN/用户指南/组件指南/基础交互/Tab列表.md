# Tab列表 {#concept_wp5_zqs_gfb .concept}

Tab列表是基础交互组件的一种，支持自定义Tab的颜色、数量、类型以及标签样式等，可以通过交互配置，与其他组件配合使用，在大屏中展示所选择Tab的标签内容。本文档为您介绍Tab列表各配置项的含义，帮助您快速准确地使用Tab列表组件。

## 样式 {#section_p4j_trq_gfb .section}

-   **基础属性** 

    -   图表尺寸：组件的宽度和高度，单位为px。
    -   图表位置：组件在大屏中的位置，通过横纵坐标来定义，单位为px。
    -   其他：组件的旋转角度和透明度。
-   **字体**：组件的字体。
-   **背景色**：组件的背景颜色。
-   **行数**：Tab列表的行数。
-   **列数**：Tab列表的列数。
-   **选择类型**：Tab列表的选择类型，可选：**单选**和**多选**。
-   **初始化值**：请填入期望初始化选中的标签id值，需要与数据中id字段的值匹配。当组件的**选择类型**为**单选**时，该选项只能包括一个值。当组件的**选择类型**为**多选**时，该选项可以包含多个值，多个值之间用英文逗号隔开。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155894130712905_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155894130712906_zh-CN.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155894130712909_zh-CN.png)

-   **全部按钮**：勾选后，Tab列表中会出现**全部**的Tab选项卡。只有当组件的**选择类型**为**多选**时，此选项才会显示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155894130712911_zh-CN.png)

-   **初始化全选**：勾选后，组件初始化时会选中所有的Tab选项卡，且**初始化值**配置项隐藏。只有当组件的**选择类型**为**多选**时，此选项才会显示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155894130712914_zh-CN.png)

-   **标签默认配置**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155894130712929_zh-CN.png)

    -   **字号**：组件标签的字号大小。
    -   **字体颜色**：组件标签的字体颜色，可参考[颜色选择器说明](intl.zh-CN/用户指南/组件指南/配置项说明.md#section_kdw_vj4_t2b)进行修改。
    -   **字体粗细**：组件标签的字体粗细。
    -   **背景颜色**：Tab选项卡的背景颜色。
    -   **圆角半径**：Tab选项卡的圆角半径，值越大，边角越圆。默认为0，即为长方形。
    -   **悬浮背景色**：Tab选项卡的悬浮背景色。只有在预览或者发布页面，才能看到配置效果。
    -   **选中文字色**：Tab选项卡被选中时文字的颜色。
    -   **选中背景色**：Tab选项卡被选中时的背景颜色。
-   **交互**：组件之间数据联动的变量，需要配置为数据中的某一个字段。

    **说明：** 此功能已更新到**交互**面板中， **配置**面板的该功能将弃用，请尽快升级。新版本的交互功能支持配置多个字段。


## 数据 {#section_llq_l3t_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155894130712930_zh-CN.png)

上图中的示例数据如下：

``` {#codeblock_u3m_f2r_vi8}
[
  {
    "id": 1,
    "content": "TAB1"
  },
  {
    "id": 2,
    "content": "TAB2"
  },
  {
    "id": 3,
    "content": "TAB3"
  }
]
```

-   id：Tab选项卡的标签id，**初始化值**配置项需要使用此变量的值，来定义初始化选中的Tab标签。
-   content：Tab选项卡的标签名称。

## 交互 {#section_d3q_2sr_gfb .section}

勾选**启用**，开启组件交互功能。当点击Tab标签时，会触发数据请求，抛出回调值，动态加载标签的内容。默认抛出数据中的id和content值，具体配置请参考[组件回调ID配置](../intl.zh-CN/最佳实践/配置数字翻牌器组件的回调ID.md#)。

