# Choropleth Layer {#concept_t4t_zb5_qfb .concept}

You can present area boundaries and render area styles based on data in the GeoJSON format by using the choropleth layer.

## Style {#section_p4j_trq_gfb .section}

-   **Display**: Select to display the choropleth layer. Clear the check box to hide the choropleth layer.
-   **Height**: Drag the slider or enter a value to modify the distance between the choropleth layer and the earth layer.
-   **Outline Only**: Select the check box to display only the outlines. Clear the check box to highlight the areas. You can configure the styles of the areas and the outlines.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41466/155808478121444_en-US.png)

    -   **Minimum**: Modify the color of the area whose value field in the data tab is set to the minimum value. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Maximum**: Modify the color of the area whose value field in the data tab is set to the maximum value. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **None**: Modify the color of the area whose value field in the data tab is not specified. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Fill Opacity**: Drag the slider or enter a value to modify the opacity of the highlighted areas.
-   **Outline Color**: Modify the color of the outlines. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
-   **Outline Opacity**: Drag the slider or enter a value to modify the opacity of the outlines.
-   **Outline Thickness**: Drag the slider or enter a value to modify the width of the outlines.

## Data {#section_w1h_wqr_gfb .section}

-   **Geographical Data**: Customize the geographical data to define an area at the choropleth layer. The format of the data is GeoJSON. For more information about the format and how to obtain data, see [Map Data Format](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Map Data format.md#).
-   **Choropleth Layer**:

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41466/155808478130594_en-US.png)

    -   adcode: The address code \(adcode\) of the area.
    -   value: The value of the area. The color of an area is determined by the Maximum and Minimum fields in the style tab and the value field in the data tab.

        **Note:** The value field of an area determines where the color of the area is located in the color gradient.


## Interaction {#section_y13_b3y_gfb .section}

This widget is not bound to any events.

