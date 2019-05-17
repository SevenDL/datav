# Flying Route Layer {#concept_qgw_1kz_qfb .concept}

Flying Route Layer uses lines to visualize origin-destination \(OD\) data, representing the connection between two locations such as logistics and trades.

## Style {#section_p4j_trq_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41506/155808495221742_en-US.png)

-   **Show**: Select the Show check box to show the flying route layer. Clear the check box to hide the flying route layer.
-   **Flying Route Radius**: Drag the slider or enter a number manually to adjust the radius of the scanner layer.
-   **Flying Route Length**: Drag the slider or enter a number manually to adjust the length of the flying lines.
-   **Flying Route Speed**: Drag the slider or enter a number manually to adjust the moving speed of the flying lines.
-   **Flying Route Height**: Drag the slider or enter a number manually to adjust the height of the flying route layer from the surface of the globe.
-   **Flying Route Arc**: Drag the slider or enter a number manually to adjust the curvature of the flying lines.
-   **Flying Route Opacity**: Drag the slider or enter a number manually to adjust the opacity of the flying lines.
-   **Default Color**: If the type of a flying line in the data source is not contained in the Flying Route Type property, then the default color is rendered for the flying line. For more information about how to modify the default color, see [Color selector](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
-   **Flying Route Type**: The property contains the **Type** property and the **Color** property. The values of these two properties can be considered as the elements of two arrays. The values of the **type** properties for each flying route type are a subset of the values of the type properties that are specified for each flying line in the data source. If the type of a flying line in the data source is not included in the values of the **type** properties contained in the Flying Route Type property, then the **default color** is rendered for the flying line.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41506/155808495321477_en-US.png)

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41506/155808495321478_en-US.png)


## Data {#section_w1h_wqr_gfb .section}

-   from: The start point of a flying line specified by the longitude and the latitude, which are separated by an English comma.
-   to: The end point of a flying line specified by the longitude and the latitude, which are separated by an English comma.
-   type: The alias of the color of a flying line. It is used in combination with the **Flying Route Type** property in the Style pane.

## Interaction {#section_y13_b3y_gfb .section}

The component does not have any interaction events.

