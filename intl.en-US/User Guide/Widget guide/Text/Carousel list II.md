# Carousel list II {#concept_br5_zpx_gfb .concept}

The carousel list II widget allows you to customize the carousel list style, the animation and display of content in the carousel list, and other options as needed.

## Style {#section_ycw_lxr_q2b .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Global**
    -   **Number of Rows**: To change the number of rows in the carousel list, enter a value, or click **+** or **–**.
    -   **Loop**: If you select this option, content in the carousel list will be automatically displayed in a looped sequence on the preview or publish page. If you clear this option, you cannot set the animation style.
    -   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
-   **Animation**
    -   **Mode**: To set the animation mode, click the drop-down arrow and select the target mode.
        -   Scroll all
        -   Scroll one by one
    -   **Interval**: To change the time interval between the display of two pages, enter a value, or click **+** or **–**. The unit is seconds.
    -   **Single Page Stop**: If you select this option, content in the list is displayed only once when there is only one page.
-   **Hide Empty Row**: If you select this option, the row or rows with no data are hidden.
-   **Overflow Text Scrolling**

    -   **Scrolling**: If you select this option, the overflow text will be automatically scrolled on the preview or publish page.
    -   **Animate Interval**: To change the scroll duration, enter a value, or click **+** or **–**. The unit is seconds.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21839/155808292512904_en-US.png)

-   **Header**: To display the table header, click the **Eye** icon.

    -   **Header Height**: To change the proportion of the header in the list, enter a value or drag the slider. The value range is from 0 to 100, and the unit is %.
    -   **Background Color**: To change the background color of the table header, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Text Style**
        -   **Text Align**: To set the text alignment method, click the drop-down arrow and select the target method.
            -   Align left
            -   Center alignment
            -   Align right
        -   **Font Family**: To set the font of the table header text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
        -   **Font Color**: To change the font color of the table header text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Size**: To change the font size of the table header text, enter a value or drag the slider. The value range is from 0 to 200.
        -   **Font Weight**: To change the font weight of the table header text, click the drop-down arrow and select the target font weight.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21839/155808292512937_en-US.png)

-   **Row Options**

    -   **Odd Rows Background**: To change the background color of the odd rows, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Even Rows Background**: To change the background color of the even rows, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Callback ID**: You can set the values of a row as the callback IDs as needed.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21839/155808292512942_en-US.png)

-   **Index**: To display the index numbers, click the **Eye** icon.

    -   **Background Color**: To change the background color of the index numbers, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Width**: To change the width of the index numbers, enter a value or drag the slider. The value range is from 0 to 100, and the unit is %.
    -   **Radius**: To change the radius of the space occupied by the index numbers, enter a value or drag the slider. The value range is from 0 to 100, and the unit is %.
    -   **Text Style**
        -   **Font Color**: To change the font color of the index numbers, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Size**: To change the font size of the index numbers, enter a value or drag the slider. The value range is from 0 to 50.
        -   **Font Weight**: To change the font weight of the index numbers, click the drop-down arrow and select the target font weight.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21839/155808292512943_en-US.png)

-   **Columns**: To add a label, click **+**. To delete a label, click the **Trash** icon.

    **Note:** A column is an array. You can set two or more columns as needed, and the Editor traverses and renders the data through the column settings. To set data in a specific format, sort the data manually.

    -   **Name in Data**: You can set a name for the column as needed. The column name of each label corresponds to a field in the data pane.
    -   **Displayed Name**: You can customize the displayed name of a column as needed. The displayed name of a label is displayed as the table header of a column in the carousel list.
    -   **Width**: To change the spacing between the labels, enter a value or drag the slider. The value range is from 0 to 100, and the unit is %.
    -   **Data Type**: To set the display format of the data, click the drop-down arrow and select the target format.
        -   Text
        -   Image
    -   **Wrap Automatically**: If you select this option, the label content is wrapped automatically.
    -   **Text Style**
        -   **Text Align**: To set the text alignment method, click the drop-down arrow and select the target method.
            -   Align left
            -   Center alignment
            -   Align right
        -   **Font Size**: To change the font size of the label text, enter a value or drag the slider. The value range is from 0 to 200.
        -   **Font Color**: To change the font color of the label text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To change the font weight of the label text, click the drop-down arrow and select the target font weight.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21839/155808292512944_en-US.png)


## Data {#section_atz_kyr_q2b .section}

-   You can set the fields in the data pane as needed. Values of these fields must correspond to the column name of each label set in **Columns**. You can add a pair of HTML **a** tags to the value of these fields.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21839/155808292512962_en-US.png)

## Interaction {#section_fdw_khz_gfb .section}

To enable the interaction function, select **Enable**. For more information, see [Configure callback IDs for ticker boards](../intl.en-US/Best Practices/Configure callback IDs for ticker boards.md#).

