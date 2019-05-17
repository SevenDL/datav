# Configure a basemap layer {#concept_pct_hf5_q2b .concept}

This topic describes how to configure a basemap layer \(also called a tile layer\) that functions as a basic flat map background.

## Prerequisites {#section_mcs_3pc_fhb .section}

The basemap layer child widget is added to the basic flat map, and the widget parameters are set. For more information, see [Configure a basic flat map](intl.en-US/User Guide/Widget guide/Basic flat map widgets/Configure a basic flat map.md#).

## Configure the configuration plane {#section_urf_jvl_cgb .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16573/155808639541120_en-US.png)

-   **Mask Color**: Set the mask color of the basemap layer. For more information, see [Configure item description](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#).
-   **Opacity**: Set the opacity of the basemap layer by dragging the slider or entering a value. The value range of this parameter is 0 to 1.
-   **TileUrl**: Enter a tile URL in the box. DataV supports the following map tile service URLs:
    -   **GeoQ map** 
        -   GeoQ misty gray. Its URL is //map.geoq.cn/ArcGIS/rest/services/ChinaOnlineStreetGray/MapServer/tile/\{z\}/\{y\}/\{x\}
        -   GeoQ midnight blue. Its URL is //map.geoq.cn/ArcGIS/rest/services/ChinaOnlineStreetPurplishBlue/MapServer/tile/\{z\}/\{y\}/\{x\}
        -   GeoQ color. Its URL is //map.geoq.cn/ArcGIS/rest/services/ChinaOnlineCommunity/MapServer/tile/\{z\}/\{y\}/\{x\}
        -   GeoQ edge. Its URL is //thematic.geoq.cn/arcgis/rest/services/ThematicMaps/administrative\_division\_boundaryandlabel/MapServer/tile/\{z\}/\{y\}/\{x\}
    -   **Amap** 
        -   Electronic map of amap.com. Its URL is http://webst02.is.autonavi.com/appmaptile?style=7&x=\{x\}&y=\{y\}&z=\{z\}
        -   Satellite map of amap.com. Its URL is http://webst02.is.autonavi.com/appmaptile?style=6&x=\{x\}&y=\{y\}&z=\{z\}
        -   Satellite map \(road networks and annotations\) of amap.com. Its URL is http://webst02.is.autonavi.com/appmaptile?style=8&x=\{x\}&y=\{y\}&z=\{z\}
    -   **Google MapS** 
        -   Google electronic map. Its URL is `http://www.google.cn/maps/vt?lyrs=m@189&gl=cn&x={x}&y={y}&z={z}`.
        -   Google satellite map. Its URL is `http://mt3.google.cn/vt/lyrs=s&hl=zh-CN&gl=cn&x={x}&y={y}&z={z}`.
-   **Auto Refresh**: Select this check box to enable the auto refresh function.

    **Note:** You must enable this function to obtain the latest map tile service data if you use the tile URL of the Amap heat service or the Amap real-time traffic status service.

    **Refresh Interval**: Set the interval \(in minutes\) at which the tile service is automatically refreshed.

-   **Use Filter**: Select this check box to add a filter effect to the basemap layer.
-   **Filter**: Set the filter parameters, including **Brightness**, **Contrast**, **Grayscale**, **HueRotate**, **Invert**, **Saturate**, and **Sepia**.

## Configure the data plane {#section_wkf_2pc_fhb .section}

No settings are required.

## Configure the interaction plane {#section_blq_2pc_fhb .section}

No settings are required.

