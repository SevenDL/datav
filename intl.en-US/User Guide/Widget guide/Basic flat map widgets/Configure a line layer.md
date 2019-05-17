# Configure a line layer {#concept_qcc_kf5_q2b .concept}

This topic describes how to configure a line layer to indicates data points \(for example, railways\) by using lines.

## Prerequisites {#section_ad4_5rc_fhb .section}

The line layer child widget is added to the basic flat map and the widget parameters are set. For more information, see [Map container](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Configure a basic flat map.md#).

## Configure the configuration plane {#section_rnx_zfp_dgb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16576/155808661441121_en-US.png)

-   **Stroke Options**
    -   **Color**: Set the values for **MinValue Color**, **MaxValue Color**, and **NoData Color**.

        -   **MinValue Color** indicates the color of the line that has the minimum value in the `value` field.
        -   **MaxValue Color** indicates the color of the line that has the maximum value in the `value` field.
        -   **NoData Color** indicates the color of the line that has no value in the `value` field.
        If the value indicated by a line is between the maximum value and the minimum value, the color of the line is a gradient color calculated based on the value. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16576/155808661441122_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16576/155808661441123_en-US.png)

        **Note:** If the **Color** values in both the **Configuration** plane and the color field in the **Data** plane are set, the **Data** plane value takes effect.

    -   **LineWidth**: Set the line width by dragging the slider or entering a value.
    -   **Dotted Line**: Select a line type from the drop-down list.
-   **Interactive Options**
    -   **Hover**: Enable or disable the hover function by clicking the **Eye** icon. You can set the color and width of the line displayed for the hover effect. This effect is displayed only when you preview the layer or after you release the layer.
    -   **Click FitBounds**: Select this check box to enable the focus effect for the line. After you enable this effect, the system automatically focuses the line that you have clicked. The line focus effect is displayed only when you preview the layer or after you release the layer.
    -   **FitBounds Padding**: Set the fitbounds padding of lines by dragging the slider. You must select the **Click FitBounds** check box before setting this parameter. The padding setting is displayed only when you preview the layer or after you release the layer.
    -   **Callback ID**: Set the field for associating data between widgets. This filed must be associated with the data of this widget, and you can only set one field for this parameter.

        **Note:** This function is also added to the **Interaction** plane where you can set multiple fields. Additionally, this function will be removed from the **Configuration** plane. Therefore, we recommend that you upgrade the widget to the latest version.


## Configure the data plane {#section_fzm_1gp_dgb .section}

The following two data sources are required: **GeoJSON LineString data** and **Mapping data**.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16576/155808661441124_en-US.png)

-   **GeoJSON LineString data**: Set the GeoJSON LineString data. If you want to associate this type of data with the mapping data, you must ensure that this type of data has a unique link\_id or id field. For more information, see [http://geojson.org/geojson-spec.html](http://geojson.org/geojson-spec.html).

    ```
    {
    "type": "FeatureCollection",
    "features": [
      {
        "type": "Feature",
        "properties": {
          "link_id": 1,
          "name": "test"
        },
        "geometry": {
          "type": "LineString",
          "coordinates": [
            [
              109.4677734375,
              41.409775832009565
            ],
            [
              117.46582031249999,
              36.31512514748051
            ],
            [
              118.828125,
              32.0639555946604
            ],
            [
              114.9169921875,
              27.566721430409707
            ]
          ]
        }
      }
    ]
    }
    ```

    **Note:** You can use the properties field to set messages in a pop-up box.

-   **Mapping data**

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16576/155808661441125_en-US.png)

    -   link\_id: Set the ID by which to associate the mapping data with the GeoJSON data.
    -   value: Set the line weight. Based on this field, the settings of **MinValue Color**, **MaxValue Color**, and **NoData Color** in the **Configuration** plane take effect.
    -   info: Set the message for the pop-up box. If you do not set this field, the message displayed in the pop-up box message is the content of the properties field specified in the GeoJSON data.
    -   color: Set the fields that can be used to render the lines, such as color, weight, and dashArray.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16576/155808661441127_en-US.png)


## Configure the interaction plane {#section_s3n_1gp_dgb .section}

Select the **Enable** check box to enable the interaction function. For more information, see [Configure callback IDs for ticker boards](../../../../intl.en-US/Best Practices/Configure callback IDs for ticker boards.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16576/155808661441128_en-US.png)

