# Trajectory Layer {#concept_yjr_3tv_rfb .concept}

Trajectory Layer simulates the effect of a trajectory by showing the process of rendering the line that connects dots.

## Style {#section_p4j_trq_gfb .section}

-   **Show**: Select the Show check box to show the trajectory layer. Clear the check box to hide the trajectory layer.
-   **Height**: Drag the slider or enter a number manually to adjust the height of the trajectory layer from the surface of the globe. The value is from 0.1 to 10.
-   **Length**: Drag the slider or enter a number manually to adjust the lengths of the trajectories. The value is from 0 to 1.
-   **Trajectory Frequency**: Drag the slider or enter a number manually to adjust the time interval of repeated movements for a trajectory. The value is from 0 to 1.
-   **Speed**: Drag the slider or enter a number manually to adjust the speed of the movement for a trajectory. The value is from 0 to 0.05.
-   **Color**: For more information about how to adjust the color of trajectories, see [Color selector](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
-   **Opacity**: Drag the slider or enter a number manually to adjust the opacity of the trajectories. The value is from 0 to 1.
-   **Data Classification**: Drag the slider or enter a number manually to specify the number of data grades to classify. The property helps you to avoid the issue of rendering that is caused by the large difference between the maximum and minimum value of the value properties. You can use the property to classify data into multiple grades based on the values of the value properties under the properties properties in the data source. The value is from 2 to 7 \(integer\).
-   ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41692/155808647621673_en-US.png)

-   **Trajectory Size \(Small To Large\)**: Click the plus \( **+** \) sign or the **trash can** icon to add or delete a type.

    -   **Trajectory Width**: Enter a number manually or click the plus \(**+**\) /minus \(**-**\) sign to specify the width of the trajectories corresponding to the type.

        **Note:** The values of the properties can be considered as the elements of an array. Used in combination with Data Classification, the values increase with the ordinals of the types. For example, if the value of Type 1 is set to 10, then the size of a dot with a value of 0 to 10 in the data source is shown as the size a dot with a value of 10. If the value of Type 2 is set to 20, then the size of a dot with a value of 11 to 20 is shown as the size of a dot with a value of 20. Assuming that the value of Data Classification is set to 3, the size of a dot with a value greater than 20 is shown as the size of a dot with the value of Type 3.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41692/155808647621692_en-US.png)


## Data {#section_w1h_wqr_gfb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41692/155808647621693_en-US.png)

The component data is in GeoJSON format. For more information about data formats and data acquisition, see [Map Data format](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Map Data format.md#).

-   geometry: Specifies the value of the type property to be LineString.
-   coordinates: Specifies multiple coordinates, which are formed by longitudes and latitudes.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41692/155808647625270_en-US.png)

-   properties: Specifies the values of the originid \(representing start points\) properties and the destinationid \(representing end points\) properties in the adcode format. Specifies the values of the value properties. The value property determines the width of a trajectory in combination with the Trajectory Size property in the Style pane. The default value is 1.

## Interaction {#section_y13_b3y_gfb .section}

The component does not have any interaction events.

