# Doughnut chart {#concept_hj4_x5r_q2b .concept}

The doughnut chart widget allows you to customize the pie chart style, the display of different data dimensions, the percentage of different categories, and other options as needed.

## Style {#section_ocr_bvr_q2b .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
-   **Outer Border Color**: To change the border color of the outer circle, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16979/15580843659484_en-US.png)


-   **Label**
    -   **Distance from Label to Center**: To change the horizontal distance between the labels and the center of the chart, enter a value or drag the slider. The value range is from 0 to 1.
    -   **Distance from Vertex to Center**: To change the distance between the vertices and the center of the chart, enter a value or drag the slider. The value range is from 0 to 1. If the value is too small, the vertices will overlap in the center of the chart.
    -   **Category**: To display the categories, click the **Eye** icon.
        -   **Font Size**: To set the font size of the category text, enter a value, or click **+** or **–**.
        -   **Color**: To change the font color of the category text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the category text, click the drop-down arrow and select the target font weight.
    -   **Value**
        -   **Font Size**: To set the font size of the percentage values, enter a value, or click **+** or **–**.
        -   **Color**: To change the font color of the percentage values, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Number of Decimal Places**: To set the number of digits to the right of the decimal point, enter a value, or click **+** or **–**.
        -   **Font Weight**: To set the font weight of the percentage values, click the drop-down arrow and select the target font.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16979/15580843659485_en-US.png)

        -   **Real Value**: If you select this option, the actual data values are displayed. If you clear this option, the percentage values are displayed.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16979/15580843659487_en-US.png)

-   **Circles**
    -   **Radius**: To change the distance between the center of the chart and the outer circle, enter a value or drag the slider. The value range is from 0 to 1.
    -   **Concentric Lines**: To display the concentric lines, click the **Eye** icon.

        -   **Color**: To change the color of the concentric lines, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16979/15580843659489_en-US.png)

-   **Legend**: To display the legend items, click the **Eye** icon.
    -   **Text Style**
        -   **Font Size**: To set the font size of the legend text, enter a value, or click **+** or **–**.
        -   **Font Color**: To change the font color of the legend text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the legend text, click the drop-down arrow and select the target font weight.
    -   **Layout/Margin**

        -   **Horizontal Interval**: To change the horizontal distance between the legend items, enter a value, or click **+** or **–**.
        -   **Vertical Interval**: To change the vertical distance between the legend items, enter a value, or click **+** or **–**.
        -   **Position**: To set the position of the legend items, click the drop-down arrow and select the target position.
            -   Top center
            -   Top left
            -   Top right
            -   Bottom center
            -   Bottom left
            -   Bottom right
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16979/15580843659490_en-US.png)

-   **Series**: To add or delete a series, click **+** or click the **Trash** icon.
    -   **Color**: To set the color of a segment, which corresponds to a series, click the drop-down arrow and select the target color.
        -   Solid fill
        -   Gradient fill: You can select two colors as the gradient colors.
        -   To change the gradient angle, enter a value or drag the slider. The value range is from 0 to 360.
    -   **Inner Radius**: To change the inner radius length of a segment, enter a value or drag the slider. The value range is from 0 to 1.
    -   **Outer Radius**: To change the outer radius length of a segment, enter a value or drag the slider. The value range is from 0 to 1.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16979/15580843659491_en-US.png)

-   **Animation**: To display the animation option, click the **Eye** icon.

    -   **Original Duration**: To change the duration to which the widget renders the animation for the first time, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Reset All Sectors in Pie Chart**: If you select this option, the animation of each segment in the pie chart is displayed in sequence. If you clear this option, the animation of each segment in the pie chart is displayed at the same time.
    -   **Easing**: To set animation easing, click the drop-down arrow and select the target effect.
    -   **Animations of All Series in Sequence**: If you select this option, the animations of all segments in the pie chart are displayed in sequence. If you clear this option, the animations of all segments in the pie chart are displayed at the same time.
    -   **Duration for Data Update**: To change the animation duration when data changes, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Update from Latest Status**: If you select this option, the animation begins from the segment where the data has changed. If you clear this option, the animation begins from the starting point.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16979/155808436514389_en-US.png)


## Data {#section_vzq_pvr_q2b .section}

-   x: name of a series
-   y: actual data value of a series. The value of this field determines the percentage value of a segment.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16979/15580843669488_en-US.png)


## Interaction {#section_y13_b3y_gfb .section}

This widget is not connected to any events yet.

