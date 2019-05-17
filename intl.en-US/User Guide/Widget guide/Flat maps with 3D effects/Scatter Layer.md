# Scatter Layer {#concept_e3c_qv1_rfb .concept}

You can set points on the map using the scatter layer. A point indicates the information of the specified geographic coordinates.

## Style {#section_p4j_trq_gfb .section}

-   **Scale**: Drag the slider or enter a value to set the distance from the scatter layer to the flat map. The range of the value is 0–20.
-   **Animation Range**: Drag the slider or enter a value to set the animation range of the points. The animation range is affected by the radius of the point. The range of the value is 0–3.
-   **Animation Speed**: Drag the slider or enter a value to set the animation speed. The range of the value is 0–0.2.
-   **MaxValue Radius**: Drag the slider or enter a value to set the maximum radius of the points. The radius of a point is determined by both the value field in the data tab and the configurations in the style tab. The range of the value is 1–100.
-   **MinValue Radius**: Drag the slider or enter a value to set the minimum radius of the points. The radius of a point is determined by both the value field in the data tab and the configurations in the style tab. The range of the value is 1–50.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41626/155808569021501_en-US.png)

-   **Scatter Style**

    -   **Inner Color**: You can modify the inner color of the points. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Outer Color**: You can modify the outer color of the points. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Gradient Level Count**: Drag the slider or enter a value to set the number of levels in the gradient. The animation becomes smoother if you increase the number of levels. The range of the value is 1–40.
    -   **Gradient Type**: Select a gradient type from the drop-down list.
        -   Linear None
        -   Quartic InOut
        -   Quartic Out
        -   Quartic In
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41626/155808569021502_en-US.png)


## Data {#section_w1h_wqr_gfb .section}

-   lng: The longitude of the point.
-   lat: The latitude of the point.
-   value: The value of the point. The size of a point is determined by both the value field and the configurations in the style tab.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41626/155808569021503_en-US.png)

## Interaction {#section_y13_b3y_gfb .section}

This widget is not bound to any events.

