# Tab {#concept_wp5_zqs_gfb .concept}

The tab widget allows you to customize the tabs in a project as needed. You can connect the tabs to different events in the interaction pane.

## Style {#section_p4j_trq_gfb .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font.
-   **Background Color**: To set the background color of the displayed text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
-   **Number of Rows**: To change of the number of rows in the tab list, enter a value, or click **+** or **–**.
-   **Number of Columns**: To adjust of the number of columns in the tab list, enter a value, or click **+** or **–**.
-   **Select Type**: This option contains **Single Select** and **Multiple Select**. To set the selection type, click the drop-down arrow and select the target type.
-   **Init Value**: You can enter the ID of the tag to be initialized. The ID must match the value of the id field in the data pane. If you set **Select Type** to **Single Select**, you can enter one ID only. If you set **Select Type** to **Multiple Select**, you can enter two or more IDs. However, you need to separate the IDs with commas \(,\).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155808193012905_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155808193012906_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155808193012909_en-US.png)

-   **All Buttons**: This option is displayed only after you set **Select Type** to **Multiple Select**. If you select this option, the **All** tab is displayed in the tab list.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155808193012911_en-US.png)

-   **Init All**: This option is displayed only after you set **Select Type** to **Multiple Select**. If you select this option, all tabs in the tab list are selected, and the **Init Value** option is hidden.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155808193712914_en-US.png)

-   **Label Options**

    -   **Font Size**: To change the font size of the label text, enter a value or drag the slider.
    -   **Font Color**: To change the font color of the label text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Font Weight**: To set the font weight of the label text, click the drop-down arrow and select the target font weight.
    -   **Background Color**: To set the background color of the label text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Border Radius**: To change the border radius of each tab, enter a value or drag the slider. The default value is 0.
    -   **Hover Color**: To change the color of each tab when you rest your pointer on the tab, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b). The configured color can only be viewed on the preview or publish page.
    -   **Selected Color**: To change the font color of the text on the selected tab, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Selected Background Color**: To change the background color of the selected tab, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155808193712929_en-US.png)

-   **Interaction**: You can set the callback ID for the widget as needed.

## Data {#section_llq_l3t_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21835/155808193712930_en-US.png)

-   id: tab ID, which corresponds to the value of the **Init Value** field in configuration pane
-   content: tab name

## Interaction {#section_d3q_2sr_gfb .section}

To enable the interaction function, select **Enable**. For more information, see [Configure callback IDs for ticker boards](../intl.en-US/Best Practices/Configure callback IDs for ticker boards.md#).

