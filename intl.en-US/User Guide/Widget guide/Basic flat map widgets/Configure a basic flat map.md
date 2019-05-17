# Configure a basic flat map {#concept_z4z_2f5_q2b .concept}

This topic describes how to configure the style, data, and interaction of a basic flat map.

## Configure the configuration plane {#section_iwt_435_q2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16572/15580863558528_en-US.png)

-   **Component Management**
    -   To add a widget, follow these steps:
        1.  In the DataV console, click the basic flat map, and click the **Configuration** tab.
        2.  Click **+** on the left of **Component Management**.
        3.  Select one or more widgets and click **Add Child Widget**. The names of the added widgets are displayed in the **Component Management** area.

            ![](images/39963_en-US.png)

        4.  Click a widget and configure the widget parameters, as shown in the following figure.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16572/15580863558531_en-US.png)

        5.  Go back to the configuration plane of the basic flat map to configure other widgets.
    -   In the **Component Management** area, you can click ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16572/155808635539964_en-US.png) to copy a widget, click ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16572/155808635539965_en-US.png) to rename a widget, or click ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16572/155808635639966_en-US.png) to delete a widget.

        **Note:** For more information about how to manage widgets, see [Manage child widgets of a map widget](intl.en-US/User Guide/Manage widgets/Manage child widgets of a map widget.md#).

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Global Options**: Set the map parameters, including the background color, zoom level, longitude and latitude of the map center, and scale ruler.

    -   **Background**: Set the background color of the map. For more information, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Zoom level**: Adjust the zoom level by dragging the slider or entering a zoom value.

        **Note:** The value of the zoom level can be a whole or decimal value.

    -   **Map Center**: Adjust the longitude and latitude of the map center by dragging the slider or entering a value.
    -   **Scale Ruler**: Click the **Eye** icon to enable or disable the **Scale Ruler** function. If this function is enabled, you can adjust the font color and line color of the scale ruler.
    -   **Draggable**: Select this check box to allow the map to be dragged by clicking it. This setting takes effect only when you preview the map or after you publish the map.
    -   **Zoomable**: Select this check box to allow the map to be zoomed in or zoomed out by scrolling up or scrolling down. This setting takes effect only when you preview the map or after you publish the map.
    -   **Interactive**: Select this check box to enable the interaction function. When you preview a widget or after you release a widget, you can click an area to view the data of this area.
    **Note:** You can also adjust the map center point and zoom level by configuring the data source.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16572/15580863568529_en-US.png)

    The following is an example of data in the data source:

    ```
    [
         {
           "zoom": 4,
           "lng": 112,
           "lat": 34
         }
       ]
    ```


## Configure the data plane {#section_amg_cj5_q2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16572/15580863568530_en-US.png)

-   zoom: Optional. Set the zoom level of the map. The zoom field corresponds to the **Zoom Level** field on the **Configuration** tab. If you set the zoom level for both zoom and **Zoom Level**, the value of zoom is used.
-   lng: Optional. Set the longitude of the map center. The lng field corresponds to the **Longitude** field on the **Configuration** tab. If you set the longitude for both lng and **Longitude**, the value of lng is used.
-   lat: Optional. Set the latitude of the map center. The lat field corresponds to the **Latitude** field on the **Configuration** tab. If you set the latitude for both lat and **Latitude**, the value of lat is used.

## Configure the interaction plane {#section_jnm_kj5_q2b .section}

The basic flat map does not support the configuration of callback IDs.

However, some child widgets, such as the choropleth layer, region drill-down heat layer, line layer, and scatter layer, support callback IDs. The configuration of callback IDs allows you to implement map interactions. For more information, see [Configure widget interaction](intl.en-US/User Guide/Manage widgets/Configure widget interaction.md#) and [Configure callback IDs for ticker boards](../intl.en-US/Best Practices/Configure callback IDs for ticker boards.md#).

