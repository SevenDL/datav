# Basic line chart {#concept_vsp_q3t_q2b .concept}

The basic line chart widget allows you to customize the chart style, the display of different series of data, and other options as needed.

## Style {#section_ycw_lxr_q2b .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Global Settings**
    -   **Font Family**: To set the font of the displayed text, select the target font from the drop-down list. The default font is **Microsoft YaHei**.
    -   **Margin**: Spacing between the chart and the chart borders. The unit is pixels.
    -   **Empty Data**: If you select this check box, the line and the x-axis intersect at the point where the value corresponding to the y-axis is 0. If you clear this check box, the line and the x-axis do not intersect at the point where the value corresponding to the y-axis is 0.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833329546_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833329545_en-US.png)

-   **X Axis**: To display the x-axis, click the **Eye** icon.
    -   **Text Style**
        -   **Font Size**: To change the font size of the text along the x-axis, enter a value, or click **+** or **–**.
        -   **Font Color**: To change the font color of the text along the x-axis, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the text along the x-axis, select the target font weight from the drop-down list.
    -   **Axis Label**: To display the axis labels, click the **Eye** icon.

        **Note:** An error will be displayed if the data format differs from the data format set for the x field in the data pane.

        -   **Data Type**: To set the data type along the x-axis, select the target type from the drop-down list.
            -   Numeric
            -   Category
            -   Time
        -   **Data Format**: To set the format of the data, select the target format from the drop-down list.

            **Note:** The following is an example: %Y/%m/%d%H:%M:%S.

        -   **Display Format**: To set the display format of the data, select the target format from the drop-down list.

            **Note:** Time format: %m/%d%Y%H:%M:%S; integer format: d; floating-point number: .1f.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833329547_en-US.png)

        -   **Margin**: If you select this check box, spacing 1 \(spacing between the chart and the y-axis\) and spacing 2 \(spacing between the chart and the right border of the chart\) are displayed. If you clear this check box, spacing 1 and spacing 2 are not displayed.
        -   **Margin Size**: To adjust spacing 1 and spacing 2, enter a value or drag the slider. The value range is from 0 to 1.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833329548_en-US.png)

        -   **Min/Max**: You can set the minimum and maximum values along the x-axis as needed.
        -   **Offset**: To adjust the spacing between the labels along the x-axis, enter a value, or click **+** or **–**.
        -   **Unit**: You can customize the unit of the text along the x-axis as needed.
        -   **Quantity**: To change the number of x-axis labels, enter a value, or click **+** or **–**.
        -   **Angle**: To set the angle of the x-axis labels, select the target angle from the drop-down list. The options include horizontal, slant, and vertical.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833339549_en-US.png)

        -   **Axis Line**: To display the axis line, click the **Eye** icon. To change the color of the axis line, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Grid Lines**: To display the grid lines, click the **Eye** icon. To change the color of the grid lines, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833339550_en-US.png)

-   **Y Axis**

    For more information about how to set the y-axis, see [X Axis](#).

-   **Legend**: To display the legend items, click the **Eye** icon.
    -   **Text Style**
        -   **Font Size**: To change the font size of the legend text, enter a value, or click **+** or **–**.
        -   **Font Color**: To change the font color of the legend text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the legend text, select the target font weight from the drop-down list.
    -   **Layout**

        -   **Margin**
            -   **Horizontal Interval**: To adjust spacing 1 \(spacing between the legend items and the right border of the chart\) and spacing 2 \(spacing between the legend items and the left border of the chart\), enter a value, or click **+** or **–**. The setting takes effect only when two or more series are set.
            -   **Vertical Interval**: To adjust spacing 1 \(spacing between the legend items and the top border of the chart\) and spacing 2 \(spacing between the legend items and the bottom border of the chart\), enter a value, or click **+** or **–**.
        -   **Position**: To set the position of the legend items, select the target position from the drop-down list.
            -   Top center
            -   Top left
            -   Top right
            -   Bottom center
            -   Bottom left
            -   Bottom right
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833339551_en-US.png)

-   **Series**: To add or delete a series, click **+** or click the **Trash** icon.

    **Note:** A series is an array. You can set two or more series as needed, and the Editor traverses and renders the data through the series settings. To set data in a specific format, sort the data manually.

    -   **Series Name**: You can set a name for the series as needed. If the series does not have a name, the value of the s field is displayed as the series name. If the s field does not exist, the value null is used.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833339552_en-US.png)

    -   **Line**
        -   **Color**: To change the line color, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Style**: To set the line style, select the target style from the drop-down list.
            -   Solid line
            -   Dotted line
        -   **Width**: To change the line width, enter a value, or click **+** or **–**.
        -   **Curve**: If you select this check box, the line is displayed as a curve. If you clear this check box, the line is displayed as a straight line.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833339553_en-US.png)

    -   **Point Style**: To display the point style, click the **Eye** icon.
        -   **Color**: To change the point color of the line, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Radius**: To change the point radius, enter a value, or click **+** or **–**.
    -   **Area**: To set the fill color type, select the target type from the drop-down list.

        -   Solid fill
        -   Gradient fill
            -   You can select two colors as the gradient colors.
            -   To change the gradient angle, enter a value or drag the slider. The value range is from 0 to 360.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833339554_en-US.png)

    -   **Label**: To display the labels, click the **Eye** icon.

        -   **Font Size**: To change the font size of the label text, enter a value, or click **+** or **–**.
        -   **Color**: To change the font color of the label text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the label text, select the target font weight from the drop-down list.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833339555_en-US.png)

-   **Animation**: To display the animation option, click the **Eye** icon.

    -   **Original Duration**: To change the duration to which the widget renders the animation for the first time, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Easing**: To set animation easing, select the target effect from the drop-down list.
    -   **Duration for Data Update**: To change the animation duration when data changes, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Update from Latest Status**: If you select this check box, the animation begins from the point where the data has changed. If you clear this check box, the animation begins from the starting point.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/155808333321114_en-US.png)


## Data {#section_atz_kyr_q2b .section}

-   x: data along the x-axis. The value of this field must be in the same format as the label text along the x-axis.
-   y: data along the y-axis
-   s: \(optional\) series value. If the Series Name field in Series does not have a value, the value of the s field is displayed as the series name.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/15580833339556_en-US.png)


**Example**: The following example describes how to configure the monthly evaporation and rainfall data obtained from January to July:

1.  In the **Series** area, click **Series 1** and set **Series Name** to Evaporation. Click **Series 2** and set **Series Name** to Rainfall, as shown in the following figures.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/155808333339473_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/155808333339474_en-US.png)

2.  Set the type of data along the x-axis, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/155808333339475_en-US.png)

3.  Set the display format of data along the y-axis, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/155808333339480_en-US.png)

4.  In the data pane, set **Data Source Type** to **Static Data** and configure data as follows:

    ```
    [ { "x": "January", "y": 2, "s": 1 }, { "x": "January", "y": 2.6, "s": 2 }, { "x": "February", "y": 4.9, "s": 1 }, { "x": "February", "y": 5.9, "s": 2 }, { "x": "March", "y": 7, "s": 1 }, { "x": "March", "y": 9, "s": 2 }, { "x": "April", "y": 23.2, "s": 1 }, { "x": "April", "y": 26.4, "s": 2 }, { "x": "May", "y": 25.6, "s": 1 }, { "x": "May", "y": 28.7, "s": 2 }, { "x": "June", "y": 76.7, "s": 1 }, { "x": "June", "y": 70.7, "s": 2 }, { "x": "July", "y": 135.6, "s": 1 }, { "x": "July", "y": 175.6, "s": 2 } ]
    ```

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/155808333339481_en-US.png)

    The data can be obtained from a CSV file, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/17009/155808333439482_en-US.png)

    In the CSV file, x, y, and s in the first row are the fields, and values in the second and subsequent rows are the field values. To download the CSV file, click [here](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/90155/jp_ja/1551061028524/data.csv).


## Interaction {#section_y13_b3y_gfb .section}

This widget is not connected to any events yet.

