# Heat Line Layer {#concept_b3l_32x_rfb .concept}

Scanner Layer is used to draw line elements on the positions of the globe, which are corresponding to geographic locations.

## Style {#section_p4j_trq_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41732/155808502821715_en-US.png)

-   **Show**: Select the Show check box to show the heat line layer. Clear the check box to hide the heat line layer.
-   **Dotted Line**: Select the Dotted Line check box to show the heat lines in the form of dotted lines.
-   **Height**: Drag the slider or enter a number manually to adjust the height of the heat line layer from the globe.
-   **Maximum Width**: Drag the slider or enter a number manually to adjust the maximum width of the heat lines. Specify the width of the heat line through setting the value of the value property in the data source.
-   **Gradient Speed**: Drag the slider or enter a number manually to set the flickering speed of the heat lines. The greater the value, the higher the speed.
-   **Color for Maximum**: For more information about how to adjust the color of the heat line that is corresponding to the value property that has the greatest value, see [Color selector](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
-   **Color for Minimum**: For more information about how to adjust the color of the heat line that is corresponding to the value property that has the smallest value, see [Color selector](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
-   **Maximum Transparency**: Drag the slider or enter a number manually to adjust the maximum transparency of the heat lines. The transparency of each heat line is based on the corresponding value of the value property in the data source.

## Data {#section_w1h_wqr_gfb .section}

The component data is in GeoJSON format. For more information about data formats and data acquisition, see [Map Data Format](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Map Data format.md#). Values of the value properties for each line can be configured in the properties properties.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41732/155808502821716_en-US.png)

**Note:** The range of the hexadecimal color values is calculated based on the range of values of the value properties in the data source.

## Interaction {#section_y13_b3y_gfb .section}

The component does not have any interaction events.

