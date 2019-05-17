# Map container {#concept_rk3_rv1_rfb .concept}

Flat Map with 3D Effects is a container that holds a flat map with 3D effects. You can add layers such as scatter layers, flying routes layers, and columns layers to this container, which enables you to show real-time data across the globe from multiple perspectives and in diverse forms.

## Style {#section_p4j_trq_gfb .section}

-   **Child Management**
    -   **Add a Child Widget**: Click the **+** button next to **Child Management**, select a child widget, and then click **Add a Child Widget**. The added child widget is displayed in **Child Management**.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41628/155808562521566_en-US.png)

    -   **Copy, edit, or delete a child widget**: Move the mouse over the added child widget and click ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41446/155808562521428_en-US.png) next to the child widget name to copy the child widget. Click ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41446/155808562521429_en-US.png) to edit the name of the child widget. Click ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41446/155808562521430_en-US.png) to delete the child widget.
-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Global Options**

    -   **Camera Rotation**
        -   **Horizontal**: Drag the slider or enter a value to rotate the camera horizontally. The range of the value is -180 to 180.
        -   **Vertical**: Drag the slider or enter a value to rotate the camera vertically. The range of the value is -90 to 90.
    -   **Camera Center**
        -   **Latitude**: Drag the slider or enter a value to set the latitude of the camera. The range of the value is -90 to90.
        -   **Longitude**: Drag the slider or enter a value to set the longitude of the camera. The range of the value is -180 to 180.
    -   **Camera Distance**: Drag the slider or enter a value to set the focal length of the camera. The range of the value is 18–420.
    -   **Map Interaction**: Select the check box to enable the map interaction feature. With this feature, you can create interaction events in the preview page or the published page. For example, you can create an event that is triggered by clicking. Clear the check box to disable the map interaction feature.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41628/155808562521567_en-US.png)

-   **Fill Options**
    -   **Fill Color**

        -   **MinValue Color**: You can modify the minimum value for the color. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **MaxValue Color**: You can modify the maximum value for the color. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).

            **Note:** Different countries/regions are rendered with different colors based on the value field in the data tab.

        -   **NoData Color**: You can modify the color of the countries/regions whose value fields are not specified in the data tab. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Back Side**: You can modify the color of the back of the map. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b). You can view the back of the map by rotating the camera. For example, see the second figure that follows.
        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41628/155808562521568_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41628/155808562521569_en-US.png)

    -   **Outline Options**
        -   **Outline Color**: You can modify the color of the outlines on the map. For more information, see [Color Picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Outline Width**: Click **+** or **-** or enter a value to modify the width of the outlines on the map.
        -   **Opacity**: Drag the slider or enter a value to set the opacity of the outlines on the map. The range of the value is 0–1.

## Data {#section_w1h_wqr_gfb .section}

Two fields can be configured by default in the data tab of the map container.

-   id: The abbreviation of the country/region on the map.
-   to: The value of the country/region. The color of a country/region is determined by both the value field and the configurations in the style tab.
-   name \(optional\): The full name of the country/region.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41628/155808562521585_en-US.png)

## Interaction {#section_y13_b3y_gfb .section}

This widget is not bound to any events.

