# Ticker board {#concept_vw5_yqb_kfb .concept}

The ticker board widget allows you to customize the ticker board style, the displayed content, and other options as needed.

## Style {#section_ycw_lxr_q2b .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Global Settings** 

    -   **Text Style** 
        -   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
    -   **Arrangement**: To set the position of the title, click the drop-down arrow and select the target position.
        -   Top
        -   Left
        -   Bottom
    -   **Margin**: To adjust the spacing between the title and the number, enter a value or drag the slider. The value range is from –100 to 500.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22647/155808375313382_en-US.png)

-   **Title** 

    -   **Title Name**: You can set a title for the ticker board as needed. The system can also obtain the title name from the data pane.
    -   **Text Style** 
        -   **Font Size**: To change the font size of the title text, enter a value, or click **+** or **–**.
        -   **Font Color**: To change the font color of the title text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Weight**: To set the font weight of the title text, click the drop-down arrow and select the target font weight.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22647/155808375313383_en-US.png)

-   **Ticker Board** 
    -   **Font Family**: To set the font of the text on the ticker board, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
    -   **Horizontal Alignment**: To set the horizontal alignment method of the text on the ticker board, click the drop-down arrow and select the target alignment method.
        -   Align left
        -   Align right
        -   Center alignment
    -   **Prefix** 

        -   **Content**: You can customize the prefix of the number on the ticker board as needed. The default prefix is $.
        -   **Text Style** 
            -   **Font Family**: To set the font of the prefix, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
            -   **Font Color**: To change the font color of the prefix, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
            -   **Font Size**: To change the font size of the prefix, enter a value, or click **+** or **–**.
            -   **Font Weight**: To set the font weight of the prefix, click the drop-down arrow and select the target font weight.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22647/155808375313384_en-US.png)

    -   **Numbers** 
        -   **Text Style** 
            -   **Font Color**: To change the font color of the number, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
            -   **Font Size**: To change the font size of the number, enter a value, or click **+** or **–**.
            -   **Font Weight**: To set the font weight of the number, click the drop-down arrow and select the target font weight.
        -   **Margin Right**: To adjust the spacing between the digits, enter a value or drag the slider. The value range is from 0 to 100.
        -   **Background Color**: To change the color of the blocks under the number, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Background Radius**: To change the radius of the blocks under the number, enter a value or drag the slider. The value range is from 0 to 100.
        -   **Thousands Separator Background**: If you select this option, the block under the thousands separator is displayed. If you clear this option, the block under the thousands separator is not displayed.
        -   **Default Digits**: To change the number of digits to be displayed, enter a value or drag the slider. The value range is from 0 to 100.

            **Note:** If the set value is smaller than the number of the actual digits, the system will hide the first N digits. If the set value is greater than the number of the actual digits, the system will add N zeros to the data value. \(N is the difference of the set value and the number of the actual digits.\)

        -   **Rounding**: If you select this option, the data value is rounded. If you clear this option, the data value is not rounded.
        -   **Thousands Separator**: If you select this option, a thousands separator is displayed. If you clear this option, no thousands separator is displayed.
        -   **Thousands Separator Symbol**: You can customize the thousands separator symbol as needed.

            **Note:** Only one character is allowed. If more than one character is input, the first character will be used. Numbers cannot be used as separators.

        -   **Decimal Symbol**: You can customize the decimal symbol as needed.

            **Note:** Only one character is allowed. If more than one character is input, the first character will be used. Numbers cannot be used as separators.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22647/155808375313385_en-US.png)

        -   **Always Animation**: If you select this option, the ticker board scrolls regardless of whether the data changes. If you clear this option, the ticker board does not scroll when the data does not change.

            **Note:** The animation always turns on even the input data does not change.

        -   **Animation Duration**: To change the animation duration, enter a value, or click **+** or **–**. The unit is milliseconds.
        -   **Data Correction**: If you select this option, only the data rise trend is displayed. If you clear this option, both the data rise and fall trends are displayed.
-   **Suffix** 
    -   **Content**: You can customize the suffix of the data value on the ticker board as needed. The default suffix is Dollar.
    -   **Text Style** 

        -   **Font Family**: To set the font of the suffix, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
        -   **Font Color**: To change the font color of the suffix, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Size**: To change the font size of the suffix, enter a value, or click **+** or **–**.
        -   **Font Weight**: To set the font weight of the suffix, click the drop-down arrow and select the target font weight.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22647/155808375313386_en-US.png)

-   **Interaction**: You can set the callback ID for the widget as needed. You can use a field specified in the data pane to implement data interaction between different widgets.

    **Note:** The interaction function has been migrated from the **Configuration** pane to the **Interaction** pane. Please upgrade your widget as soon as possible.

-   ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22647/155808375313387_en-US.png)


## Data {#section_atz_kyr_q2b .section}

-   name: \(optional\) title of the ticker board. The title you set here will overwrite the title you set in the configuration pane.
-   value: data value on the ticker board.
-   prefix: \(optional\) prefix of the data value on the ticker board. The prefix you set here will overwrite the prefix you set in the configuration pane.
-   suffix: \(optional\) suffix of the data value on the ticker board. The suffix you set here will overwrite the suffix you set in the configuration pane.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22647/155808375313440_en-US.png)

## Interaction {#section_d3q_2sr_gfb .section}

To enable the interaction function, select **Enable**. For more information, see [Configure callback IDs for ticker boards](../intl.en-US/Best Practices/Configure callback IDs for ticker boards.md#).

