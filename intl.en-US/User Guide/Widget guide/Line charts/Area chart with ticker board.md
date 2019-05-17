# Area chart with ticker board {#concept_qw1_33s_q2b .concept}

The widget of area chart with ticker board allows you to customize the ticker board style, the display of different series of data, and other options as needed.

## Style {#section_ycw_lxr_q2b .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Global Settings**
    -   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
    -   **Margin**: Spacing between the chart and the chart borders. The unit is pixels.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819529_en-US.png)

-   **X Axis**: To display the x-axis, click the **Eye** icon.

    -   **Text Style**
        -   **Font Size**: To change the font size of the text along the x-axis, enter a value, or click **+** or **–**.
        -   **Font Color**: To change the font color of the text along the x-axis, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To change the font weight of the text along the x-axis, click the drop-down arrow and select the target font weight.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819530_en-US.png)

-   **Axis Label**: To display the axis labels, click the **Eye** icon.

    **Note:** An error will be displayed if the data format differs from the data format set for the x field in the data pane.

    -   **Data Type**: To set the type of data along the x-axis, click the drop-down arrow and select the target type.
        -   Numeric
        -   Category
        -   Time
    -   **Data Format**: To set the format of the data, click the drop-down arrow and select the target format.

        **Note:** The following is an example: %Y/%m/%d%H:%M:%S.

    -   **Display Format**: To set the display format of the data, click the drop-down arrow and select the target format.

        **Note:** Time format: %m/%d%Y%H:%M:%S; integer format: d; floating-point number: .1f.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819531_en-US.png)

    -   **Margin**: If you select this option, spacing 1 \(spacing between the chart and the y-axis\) and spacing 2 \(spacing between the chart and the right border of the chart\) are displayed. If you clear this option, spacing 1 and spacing 2 are not displayed.
    -   **Margin Size**: To adjust spacing 1 and spacing 2, enter a value or drag the slider. The value range is from 0 to 1.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819532_en-US.png)

    -   **Min/Max**: You can set the minimum and maximum values along the x-axis as needed.
    -   **Unit**: You can customize the unit of the text along the x-axis as needed.
    -   **Quantity**: To change the number of labels along the x-axis, enter a value, or click **+** or **–**.
    -   **Angle**: To set the angle of the labels along the x-axis, click the drop-down arrow and select the target angle. The options include horizontal, slant, and vertical.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819533_en-US.png)

    -   **Axis Line**: To display the axis line, click the **Eye** icon. To change the color of the axis line, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Grid Lines**: To display the grid lines, click the **Eye** icon. To change the color of the grid lines, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819534_en-US.png)

-   **Y Axis**

    For more information about how to set the y-axis, see [X Axis](#).

-   **Legend**: To display the legend items, click the **Eye** icon.
    -   **Text Style**
        -   **Font Size**: To change the font size of the legend text, enter a value, or click **+** or **–**.
        -   **Font Color**: To change the font color of the legend text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To change the font weight of the legend text, click the drop-down arrow and select the target font weight.
    -   **Layout**

        -   **Margin**
            -   **Horizontal Spacing**: To adjust spacing 1 \(spacing between the legend items and the right border of the chart\) and spacing 2 \(spacing between the legend items and the left border of the chart\), enter a value, or click **+** or **–**.
            -   **Vertical Spacing**: To adjust spacing 1 \(spacing between the legend items and the top border of the chart\) and spacing 2 \(spacing between the legend items and the bottom border of the chart\), enter a value, or click **+** or **–**.
        -   **Position**: To set the position of the legend items, click the drop-down arrow and select the target position.
            -   Top center
            -   Top left
            -   Top right
            -   Bottom center
            -   Bottom left
            -   Bottom right
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819535_en-US.png)

-   **Series**: To add or delete a series, click **+** or click the **Trash** icon.

    **Note:** A series is an array. You can set two or more series as needed, and the Editor traverses and renders the data through the series settings. To set data in a specific format, sort the data manually.

    -   **Series Name**: You can set a name for the series as needed. If the series does not have a name, the value of the s field is displayed as the series name. If the s field does not exist, the value null is used.
    -   **Area**

        -   **Color**: To set the fill color type, click the drop-down arrow and select the target type.
            -   Solid fill
            -   Gradient fill
                -   You can select two colors as the gradient colors.
                -   To change the gradient angle, enter a value or drag the slider. The value range is from 0 to 360.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819536_en-US.png)

    -   **Line**

        -   **Color**: To change the line color, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Style**: To change the line style, click the drop-down arrow and select the target style.
            -   Solid line
            -   Dotted line
        -   **Width**: To change the line width, enter a value, or click **+** or **–**.
        -   **Curve**: If you select this option, the line is displayed as a curve. If you clear this option, the line is displayed as a straight line.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819537_en-US.png)

    -   **Point Style**: To display the point style, click the **Eye** icon.

        -   **Color**: To change the point color of the line, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Radius**: To change the point radius, enter a value, or click **+** or **–**.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819538_en-US.png)

    -   **Label**: To display the labels, click the **Eye** icon.

        -   **Font Size**: To change the font size of the label text, enter a value, or click **+** or **–**.
        -   **Color**: To change the font color of the label text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To change the font weight of the label text, click the drop-down arrow and select the target font weight.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819539_en-US.png)

-   **Ticker Board**

    **Note:** By default, the data displayed on the ticker board is the last data that corresponds to the y-axis.

    -   **Font Color**: To change the font color of the data displayed on the ticker board, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Font Size**: To change the font size of the data displayed on the ticker board, enter a value or drag the slider. The value range is from 0 to 100.
    -   **Font Weight**: To change the font weight of the data displayed on the ticker board, click the drop-down arrow and select the target font weight.
    -   **Rounding**: If you select this option, the data value is automatically rounded. If you clear this option, the data value is not rounded.
    -   **Thousands Separator**: If you select this option, a thousands separator is inserted. If you clear this option, no thousands separator is inserted.
    -   **Prefix**: You can customize the prefix as needed.
    -   **Font Color**: To change the font color of the prefix, [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Font Size**: To change the font size of the prefix, enter a value or drag the slider. The value range is from 0 to 100.
    -   **Font Weight**: To change the font weight of the prefix, click the drop-down arrow and select the target font weight.
    -   **Suffix**: For more information about how to set the suffix, see [Prefix](#前缀).
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819542_en-US.png)

-   **Animation**: To display the animation option, click the **Eye** icon.

    -   **Original Duration**: To change the duration to which the widget renders the animation for the first time, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Easing**: To set animation easing, click the drop-down arrow and select the target effect.
    -   **Duration for Data Update**: To change the animation duration when data changes, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Update from Latest Status**: If you select this option, the animation begins from the point where the data has changed. If you clear this option, the animation begins from the starting point.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/155808338121113_en-US.png)


## Data {#section_atz_kyr_q2b .section}

-   x: data along the x-axis. The value of this field must be in the same format as the label text along the x-axis.
-   y: data along the y-axis
-   s: \(optional\) series value. If the Series Name field in Series does not have a value, the value of the s field is displayed as the series name.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16987/15580833819543_en-US.png)


## Interaction {#section_y13_b3y_gfb .section}

This widget is not connected to any events yet.

