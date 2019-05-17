# Configure an isosurface layer {#concept_vv3_4md_2gb .concept}

This topic describes how to configure an isosurface layer to convert vector point data to a raster map. For example, you can display a national air quality map by using an isosurface layer.

## Prerequisites {#section_qsc_fwb_fhb .section}

The isosurface layer child widget is added to the basic flat map and the widget parameters are set. For more information, see [Map container](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Configure a basic flat map.md#).

## Configure the configuration plane {#section_k3q_qmd_2gb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/80671/155808667041113_en-US.png)

-   **Opacity**: Set the overall layer opacity by dragging the slider or entering a value.
-   **Pixel Size**: Set the pixel size of each square of the raster graphic by clicking **+** or **-**, or entering a value. The value range of this parameter is 1 to 10. A smaller pixel size indicates a clearer isosurface layer, but takes longer to render compared with a greater a greater pixel.
-   **Weight**: Set the weight of the interpolation point by which it affects its surrounding points by dragging the slider or entering a value. The value range of this parameter is 0.5 to 3. A greater weight value indicates that the interpolation point significantly affects its surrounding points and achieves a better layering effect, but takes a longer time to render compared with a lower weight value.
-   **Render Type**: Select a layer render type from the drop-down list. Available types are **Linear** and **Piecewise**.
    -   **Linear**
        -   **From Color**: Set the color of the interpolation point that indicates the minimum value in the data source. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Middle Color**: Set the color of the interpolation point that indicates the median value in the data source. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **End Color**: Set the color of the interpolation point that indicates the maximum value in the data source. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Break Value**: Set the break value for linear rendering by dragging the slider or entering a value. Based on the specified break value and the value range in the data source, DataV obtains the interpolation point of the middle value. The color of this interpolation point is the **Middle Color** that you set.

            **Note:** This parameter setting takes effect only if you set **Render Type** to **Linear**.

        -   **Classify Color Count**: Set the number of classification of interpolation point by dragging the slider or entering a value. Based on the **Classify Color Count** value that you set and the value range in the data source, DataV uses different colors to classify interpolation points. A greater **Classify Color Count** value indicates a better interpolation effect, but takes a longer time to render compared with a lower **Classify Color Count** value.
    -   **Piecewise**
        -   **Default Color**: Set the default color of interpolation points. If the value indicated by an interpolation point is not included in the **Break Value** that you set, this parameter takes effect. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Piecewise**: Add or remove a break by clicking **+** or the **Trash Can** icon on the right.
            -   **Break Value**: Set a break by dragging the slider or entering a value. You can set this parameter according to the value range that is indicated by all interpolation points.
            -   **Break Color**: Set the color of the interpolation points that indicate values included in a **Break**. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).

## Configure the data plane {#section_pdz_qmd_2gb .section}

-   **Clip GeoJSON data**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/80671/155808667041114_en-US.png)

    The **Clip GeoJSON data** settings specify the area of interpolation points that need to be rendered. For example, in the preceding figure, the **Clip GeoJSON data** settings specify the China map displayed in colors.

-   **Interpolation Points Data**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/80671/155808667041117_en-US.png)

    -   lng: Set the longitude of the interpolation points.
    -   lat: Set the latitude of the interpolation points.
    -   value: Set the interpolation point value. Based on the value and the rendering settings in the **Configuration** plane, DataV adjusts the layer rendering effect.

## Configure the interaction plane {#section_btz_qmd_2gb .section}

No settings are required.

