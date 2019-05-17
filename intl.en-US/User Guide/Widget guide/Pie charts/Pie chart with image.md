# Pie chart with image {#concept_nl1_jmg_y2b .concept}

The pie chart with image widget allows you to customize the pie chart style, upload an image to the center of the pie chart, and customize the percentage of displayed data as needed.

## Style {#section_ocr_bvr_q2b .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
-   **Image**: To change the image in the center of the pie chart, click the **Trash** icon to delete the current image and upload a local one. To use an image stored on the Internet, enter the URL of the image.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18642/155808440110253_en-US.png)


-   **Label**
    -   **Distance from Label to Center**: To change the distance between the labels and the center of the pie chart, enter a value or drag the slider. The value range is from 0 to 1.
    -   **Distance from Vertex to Center**: To change the distance between the vertices and the center of the pie chart, enter a value or drag the slider. The value range is from 0 to 1. If the value is too small, the vertices will overlap in the center of the pie chart.
    -   **Category**: To display the categories, click the **Eye** icon.
        -   **Font Size**: To change the font size of the category text, enter a value, or click **+** or **–**.
        -   **Color**: To change the font color of the category text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the category text, click the drop-down arrow and select the target font weight.
    -   **Value**
        -   **Font Size**: To change the font size of the percentage values, enter a value, or click **+** or **–**.
        -   **Color**: To change the font color of the percentage values, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the percentage values, click the drop-down arrow and select the target font weight.
        -   **Number of Decimal Places**: To change the number of digits to the right of the decimal point, enter a value, or click **+** or **–**.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18642/155808440110278_en-US.png)

        -   **Real Value**: If you select this option, the actual data values corresponding to the percentage values are displayed.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18642/155808440110281_en-US.png)

-   **Circles**
    -   **Radius**: To change the distance between the center of the pie chart and the outer circle, enter a value or drag the slider. The value range is from 0 to 1.
    -   **Concentric Lines**: To display the concentric lines, click the **Eye** icon.

        -   **Color**: To change the color of the concentric lines, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18642/155808440110282_en-US.png)

-   **Legend**: To display the legend items, click the **Eye** icon.
    -   **Text Style**
        -   **Font Size**: To change the font size of the legend text, enter a value, or click **+** or **–**.
        -   **Font Color**: To change the font color of the legend text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the legend text, click the drop-down arrow and select the target font weight.
    -   **Layout**

        -   **Horizontal Interval**: To change the horizontal distance between the legend items, enter a value, or click **+** or **–**.
        -   **Vertical Interval**: To change the vertical distance between the legend items and the pie chart, enter a value, or click **+** or **–**.
        -   **Position**: To change the position of the legend items, click the drop-down arrow and select the target position.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18642/155808440110284_en-US.png)

-   **Series**: To add or delete a series, click **+** or click the **Trash** icon.
    -   **Color**: To set the color fill type, click the drop-down arrow and select the target type.
        -   Solid fill: To change the color of a segment, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   Gradient fill
            -   You can select two colors as the gradient colors. For more information, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
            -   To change the gradient angle, enter a value or drag the slider. The value range is from 0 to 360.
    -   **Inner Radius**: To change the inner radius length of a segment, enter a value or drag the slider. The value range is from 0 to 1.
    -   **Outer Radius**: To change the outer radius length of a segment, enter a value or drag the slider. The value range is from 0 to 1.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18642/155808440110285_en-US.png)

-   **Animation**: To display the animation option, click the **Eye** icon.

    -   **Original Duration**: To change the duration to which the widget renders the animation for the first time, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Reset All Sectors in Pie Chart**: If you select this option, the animation of each segment in the pie chart is displayed in sequence. If you clear this option, the animation of each segment in the pie chart is displayed at the same time.
    -   **Easing**: To set animation easing, click the drop-down arrow and select the target effect.
    -   **Animations of All Series in Sequence**: If you select this option, the animations of all segments in the pie chart are displayed in sequence. If you clear this option, the animations of all segments in the pie chart are displayed at the same time.
    -   **Duration for Data Update**: To change the animation duration when data changes, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Update from Latest Status**: If you select this option, the animation begins from the segment where the data has changed. If you clear this option, the animation begins from the starting point.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18642/155808440121039_en-US.png)


## Data {#section_vzq_pvr_q2b .section}

-   x: text of a category
-   y: actual data value of a series

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18642/155808440110286_en-US.png)


## Interaction {#section_y13_b3y_gfb .section}

This widget is not connected to any events yet.

