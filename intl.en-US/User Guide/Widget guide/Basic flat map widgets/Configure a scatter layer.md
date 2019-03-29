# Configure a scatter layer {#concept_z1d_fzm_cgb .concept}

This topic describes how to configure a scatter layer \(a type of data point layer\) on a map to display data across geographical locations by using scatter plot points.

## Prerequisites {#section_azp_15k_fhb .section}

The scatter layer child widget is added to the basic flat map and the widget parameters are set. For more information, see [Map container](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Map container.md#).

## Configure the configuration plane {#section_idm_mzm_cgb .section}

-   Set the **Default Options**.
    -   **Callback ID**: Set the field for associating data between widgets. This field must belong to the data of this widget, and you can only set one field for this parameter.

        **Note:** This function is also added to the **Interaction** plane where you can set multiple fields. Additionally, this function will be removed from the **Configuration** plane. Therefore, we recommend that you upgrade the widget to the latest version.

    -   **Label**: Click the **Eye** icon on the right to show or hide labels for scatter plot points.
        -   **Label Field**: Set the field to label each scatter plot point. This parameter setting must match a field of the data in the data plane. For example, if you set this parameter to **name**, each scatter plot point will be labeled by the value of the **name** field that has the same ID.

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79848/155383866241103_en-US.png)

            ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79848/155383866341104_en-US.png)

        -   **Label Color**: Set the label color. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Shadow Color**: Set the shadow color of the label. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Family**: Select a font family for the label from the drop-down list.
        -   **Font Size**: Click **+** or **-**, or enter a font size value to set the font size for the label.
        -   **Label Position**: Select a value from the drop-down list to set the position of each label relative to its corresponding scatter plot point. Available values are **Center**, **Top Center**, **Bottom Center**, **Left**, and **Right**.
    -   **Scatter Options**
        -   **Data Mapping**: Select this check box to associate the color and the size of each scatter plot point with its value field in the data source.
        -   **Fill Color**: Set the values for **MinValue Color**, **MaxValue Color**, and **NoData Color**. These three parameters take effect only if you select the **Data Mapping** check box.

            -   **MinValue Color** indicates the color of the scatter plot point that has the minimum value in the value field in the data source.
            -   **MaxValue Color** indicates the color of the scatter plot point that has the maximum value in the value field in the data source.
            -   **NoData Color** indicates the color of the scatter plot point that has no value in the value field in the data source.
            If the value field of a scatter plot point is between the maximum value and the minimum value, the system displays the scatter plot point as a gradient color according to its proportional value.

        -   **Scatter Size**: Set the values for **MinValue Size**, **MaxValue Size**, and **NoData Size**. These three parameters take effect only if you select the **Data Mapping** check box.

            -   **MinValue Size** indicates the size of the scatter plot point that has the minimum value in the value field in the data source.
            -   **MaxValue Size** indicates the size of the scatter plot point that has the maximum value in the value field in the data source.
            -   **NoData Size** indicates the size of the scatter plot point that has no value in the value field in the data source.
            If the value field of a scatter plot point is between the maximum value and the minimum value, the system displays the scatter plot point in a size according to its proportional value.

        -   **Outline Options**: Set the color and width of the outline of the scatter plot points.
    -   **Popup Options**
        -   **Font Color**: Set the color of the text in the popup box. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Font Size**: Set the size of the text in the popup box. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
-   Set the **Series Options**.

    Click the **+** or **Trash Can** icon to add or remove a scatter type.

    -   **Filter Value**: Enter a type value \(specified in the data plane\) to filter a specific type of scatter plot points. Then, you can set the icon style of the scatter plot points of this type.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79848/155383866341105_en-US.png)

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79848/155383866341106_en-US.png)

    -   **Icon Options**: Select this check box to use icons to display scatter plot points of a custom style. You can set the following **Icon** parameters: the icon image, the icon size, the icon position, and the label offset relative to the icon. If you do not select this check box, scatter plot points are displayed as dots. Then you can set the color, size, and outlines of scatter plot points. For more information, see [Set the default options](#).

## Configure the data plane {#section_n5y_mzm_cgb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79848/155383866341107_en-US.png)

-   lat: Set the latitude of the scatter plot point.
-   lng: Set the longitude of the scatter plot point.
-   type: Set the scatter plot point type. Then you can set the icon style of the custom type of scatter plot points.

    **Note:** If no type is set for a scatter plot point or its type is not included in the types that you have set, the system renders the scatter plot point according to the settings of **Default Options** in the **Configuration** plane.

-   info: Set the message of the popup box displayed when the scatter plot point is clicked.
-   iconURL: Set the URL of the custom scatter plot point icon.
-   value: Set the value of the scatter plot point. This field setting is related to the **MinValue Color**, **MaxValue Color**, and **NoData Color** settings of **Scatter Options** in the **Configuration** plane.
-   name: Set a name for the scatter plot point. This field is used when you set **Label Field** in the **Configuration** plane to label the scatter plot point.
-   rotationAngle: \(Optional.\) Set the rotation angle of the scatter plot point icon. This field takes effects only if you select the **Icon Options** check box of **Series Options** in the **Configuration** plane, and configure the icon settings \(for example, you can upload a custom icon image or set iconUrl in the data plane\).

## Configure the interaction plane {#section_rk1_nzm_cgb .section}

Select the **Enable** check box to enable the widget interaction function. With this feature enabled, the system displays the callback value when you click a scatter plot point. By default, the lng and lat fields are displayed. For more information, see [Configure callback IDs for ticker boards](../../../../../intl.en-US/Best Practices/Configure callback IDs for ticker boards.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79848/155383866341108_en-US.png)

