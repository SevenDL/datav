# Configure an animation bubbles layer {#concept_qmp_5lt_cgb .concept}

This topic describes how to configure an animated bubbles layer \(a type of data point layer\) to display data across geographical locations on a map.

## Prerequisites {#section_x4w_pbb_fhb .section}

The animation bubbles layer widget is added to the basic flat map and the widget parameters are set. For more information, see [Map container](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Configure a basic flat map.md#).

## Configure the configuration plane {#section_jt3_dmt_cgb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79890/155808653134259_en-US.png)

-   **Animation Type**: Set the type of animation for the bubbles. Available types are **Breath** and **Fading**.
-   **Animation Range**: Drag the slider or enter a value to set the size range of the bubbles. This parameter setting takes effect only if you set **Animation Type** to **Breath**.
-   **Animation Speed**: Drag the slider or enter a value to set the animation speed of the bubbles.
-   **Color Gradient Range**: Drag the slider or enter a value to set the maximum color depth of the bubbles. If you set the fading **Animation Type**, the bubble color fades from the set color depth to transparency.
-   **Max Bubble Size**: Drag the slider or enter a value to set the maximum bubble size that indicates the maximum value specified by the value field in the data plane.
-   **Min Bubble Size**: Drag the slider or enter a value to set the minimum bubble size that indicates the minimum value specified by the value field in the data plane.
-   **Bubble Type**: Click **+** or the **Trash Can** icon to add or remove a bubble type. Bubbles of one type share the same bubble style and color.
    -   **Style**: Select a bubble style from the drop-down list. Seven bubble styles are available.
    -   **Type Filter Value**: Set the bubble type value to filter bubbles. Then, you can set the same **Style** and **Color** for the filtered type of bubbles.

        **Note:** The type of each bubble is specified by the type field of this bubble in the data plane.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79890/155808653134266_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79890/155808653234267_en-US.png)

    -   **Color**: Set the color of the filtered type of bubbles. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).

## Configure the data plane {#section_c3s_dmt_cgb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79890/155808653234269_en-US.png)

-   lng: Set the longitude of the animated bubbles.
-   lat: Set the latitude of the animated bubbles.
-   value: Set the bubble value. The bubble size is determined by this parameter setting, and the **Max Bubble Size** and **Min Bubble Size** settings in the configuration plane.
-   type: Set the bubble type. This parameter setting is associated with the **Type Filter Value** setting in the configuration plane.

## Configure the interaction plane {#section_rws_dmt_cgb .section}

No settings are required.

