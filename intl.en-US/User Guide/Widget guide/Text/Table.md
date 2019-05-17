# Table {#concept_bpz_cqx_gfb .concept}

The table widget allows you to customize the table style and data arrangement as needed.

## Style {#section_ycw_lxr_q2b .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Table**
    -   **Responsive**
        -   If you select this option, the display format of the data in the table is automatically adjusted based on the table style and size when the table cells do not expand beyond the table border.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320812967_en-US.png)

        -   If you clear this option, the display format of the data in the table is no longer automatically adjusted based on the table style and size.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320812968_en-US.png)

    -   **Border Line**
        -   **Line Width**: To change the width of the border lines, enter a value, or click **+** or **–**.
        -   **Line Color**: To change the color of the border lines, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Text Style**

        -   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320812972_en-US.png)

-   **Cell**
    -   **Margin**

        -   **Left and Right Margins**: To change the left cell border margin and right cell border margin, enter a value or drag the slider. The value range is from 0 to 50.
        -   **Top and Bottom Margin**: To change the height of a cell, enter a value or drag the slider. If you select **Responsive** and the table cells do not expand beyond the table border, then your setting will be applied to the table header, and the height of the other cells will be automatically adjusted based on the table style and size. The value range for the table height is from 0 to 50.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320812974_en-US.png)

-   **Table Header**
    -   **First Row As Table Header**
        -   After you select this option, the first row of the table is styled as the table header. You can only set the table header text after you select this option. If you do not need to set the table header text, you can clear this option and remove the label and value fields from the data pane.

            -   **Text Style**
                -   **Font Color**: To change the font color of the table header text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
                -   **Font Size**: To change the font size of the table header text, enter a value or drag the slider. The value range is from 0 to 100.
                -   **Font Weight**: To set the font weight of the table header text, click the drop-down arrow and select the target font weight.
                -   **Background Color**: To change the background color of the table header, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320812975_en-US.png)

        -   If you clear the **First Row As Table Header** option, the first row of the table is not styled as the table header.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320812976_en-US.png)

-   **Column**
    -   **Width Percentage**: To change the width of the first row, enter a value, or click **+** or **–**.
    -   **Split Line**
        -   **Line Width**: To change the width of the line between two columns, enter a value, or click **+** or **–**.
        -   **Split Line Color**: To change the color of the line between two columns, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **First Column**
        -   **Text Style**
            -   **Font Color**: To change the font color of the text in the first column, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
            -   **Font Size**: To change the font size of the text in the first column, enter a value or drag the slider. The value range is from 0 to 100.
            -   **Font Weight**: To set the font weight of the text in the first column, click the drop-down arrow and select the target font weight.
        -   **Background Color**: To change the background color of the first column, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Text Align**: To set the text alignment method, click the drop-down arrow and select the target method.
            -   Align left
            -   Align right
            -   Center alignment
-   **Second Column**: For more information about how to set the second column, see [First Column](#ul_hr5_r5x_gfb).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320812992_en-US.png)

-   **Row**
    -   **Split Line**
        -   **Line Width**: To change the width of the lines between the rows, enter a value, or click **+** or **–**.
        -   **Line Color**: To change the color of the lines between the rows, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Odd-Even**
        -   If you select this option, the rows are displayed in alternating colors. You can configure the colors used to alternate between odd and even rows.

            -   **Odd Row Color**: To change the background color displayed in odd rows, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
            -   **Even Row Color**: To change the background color displayed in even rows, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320812993_en-US.png)

        -   If you clear this option, rows are no longer displayed in alternating colors. The color displayed in the rows is the column background color.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320912994_en-US.png)


## Data {#section_atz_kyr_q2b .section}

-   label: \(optional\) text in the first column of the table header
-   value: \(optional\) text in the second column of the table header

    **Note:** The values of label and value are displayed as the table header only when you select **First Row for Table Head**.


The data format in the table is as follows: \{"key in the first column":"value in the second column",...\}.

You can customize other fields as needed and display the actual data in sequence in corresponding rows.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21840/155808320912995_en-US.png)

## Interaction {#section_y13_b3y_gfb .section}

This widget is not connected to any events yet.

