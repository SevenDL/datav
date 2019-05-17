# Configure a flying routes layer {#concept_q2j_4zz_ggb .concept}

This topic describes how to configure a flying routes on a map to display the Origin-Destination \(OD\) data by using dynamic lines. Typically, a line in a flying routes layer indicates the association between two places, such as logistics and transactions.

## Prerequisites {#section_lmt_bbb_fhb .section}

The flying routes layer child widget is added to the basic flat map and the widget parameters are set. For more information, see [Map container](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Configure a basic flat map.md#).

## Configure the configuration plane {#section_p4j_trq_gfb .section}

-   **Fly Frequency**: Click **+** or **-**, or enter a value to set the frequency at which flying routes fly out.
-   **Fly Speed**: Drag the slider or enter a value to set the flight speed of flying routes. The value range of this parameter is 1 to 10.
-   **Path Points**: Drag the slider or enter a value to set the number of path points for flying routes. The value range of this parameter is 100 to 4000.
-   **Step**: Drag the slider or enter a value to set the length of flying routes. The value range of this parameter is 10 to 120.
-   **Height Ratio**: Drag the slider or enter a value to set the height ratio of flying routes. The value range of this parameter is 0.5 to 5.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/84953/155808675035561_en-US.png)

-   **Flying Style Options**
    -   **From Color**: Set the color of the starting points for flying routes. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **End Color**: Set the color of the destinations for flying routes. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Flare Color**: Set the flare color of flying routes. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Line Width**: Drag the slider or enter a value to set the width of flying routes. The value range of this parameter is 0.01 to 10.
    -   **Flare Width**: Drag the slider or enter a value to set the flare width of flying routes. The value range of this parameter is 0.01 to 20.
    -   **Gradient Ratio**: Drag the slider or enter a value to set the gradient ratio of flying routes. The value range of this parameter is 0.01 to 10.
    -   **Bubble Color**: Set the bubble color of flying routes. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Bubble Radius**: Drag the slider or enter a value to set the bubble radius of flying routes. The value range of this parameter is 0 to 30.
    -   **Bubble Speed**: Drag the slider or enter a value to set the bubble speed of flying routes. The value range of this parameter is 0.1 to 1.

## Configure the data plane {#section_w1h_wqr_gfb .section}

-   from: Set the latitude and longitude for the starting point the flying route, and use a comma \(,\) to separate the latitude and longitude.
-   to: Set the latitude and longitude for the destination of the flying route, and use a comma \(,\) to separate the latitude and longitude.

## Configure the interaction plane {#section_y13_b3y_gfb .section}

No settings are required.

