# Network diagram {#concept_hzn_gqz_gfb .concept}

This topic uses the **network diagram** widget as an example to describe how to configure networks widgets.

## Style {#section_p4j_trq_gfb .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Background Color**: To change the background color of the network diagram, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
-   **Force** 

    -   **Margin**: To adjust the position of the force-directed graph in relation to the borders, enter a value, or click **+** or **–**.
    -   **Charge**: To adjust the force of the nodes, enter a value, or click **+** or **–**. The larger the value is, the denser the nodes are clustered.
    -   **Charge Distance**: To adjust the margin between the nodes, enter a value, or click **+** or **–**.
    -   **Gravity**: To adjust the gravity of the nodes, enter a value, or click **+** or **–**. The larger the gravity is, the denser the nodes are clustered.
    -   **Friction**: To adjust the friction between the nodes, enter a value or drag the slider. The value range is from 0 to 1.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21857/155808312912998_en-US.png)

-   **Label** 

    -   **Font Color**: To change the font color of the label text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Font Size**: To set the font size of the label text, enter a value or drag the slider.
    -   **Font Weight**: To set the font weight of the label text, click the drop-down arrow and select the target font weight.
    -   **Text Align**: If you select this option, the label text is set in a position relative to the center of the nodes.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21857/155808312912999_en-US.png)

-   **Link Options** 

    -   **Stroke Color**: To change the color of the lines, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Stroke Width**: To change the width of the lines, enter a value or drag the slider.
    -   **Distance Default**: To change the length of the lines, enter a value, or click **+** or **–**.
    -   **Distance Min**: To change the minimum length of the lines, enter a value, or click **+** or **–**.
    -   **Distance Max**: To change the maximum length of the lines, enter a value, or click**+** or **–**.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21857/155808313713002_en-US.png)

-   **Node Options** 

    -   **Class Name**: You can enter a name for the center node.
    -   **Radius**: To change the radius of the center node, enter a value or drag the slider.
    -   **Fill**: To change the fill color of the center node, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Stroke Color**: To change the outline color of the center node, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Stroke Width**: To change the outline width of the center node, enter a value or drag the slider.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21857/155808313713012_en-US.png)

-   **Series Options**: To add or delete a node, click **+** or click the **Trash** icon.

    -   **Class Name**: You can enter a name for the type. If the name is not set for the type field in the data pane, the default name is used.
    -   **Radius**: To change the node radius of the same type, enter a value or drag the slider.
    -   **Fill**: To change the fill color of the nodes, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Stroke Color**: To change the outline color of the nodes, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Stroke Width**: To change the outline width of the nodes, enter a value or drag the slider.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21857/155808313713013_en-US.png)


## Data {#section_w1h_wqr_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21857/155808313713015_en-US.png)

-   nodes: node in the network diagram. The following fields are included:
    -   imgPath: image URL. If this field is empty, the nodes are displayed as circles by default.
    -   name: node name.
    -   type: node type. You can set the type in **Class Name** in the configuration pane. As shown in the preceding figure, the node whose type is set to group1 uses the name of group1.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21857/155808313713018_en-US.png)

-   links: links in the network diagram. The following fields are included:

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21857/155808313713017_en-US.png)

    -   source: source node of the lines. The value of this field is the same as the name of the source node.
    -   target: destination node of the lines. The value of this field is the same as the name of the destination node.
    -   value: line length.

## Interaction {#section_y13_b3y_gfb .section}

This widget is not connected to any events yet.

