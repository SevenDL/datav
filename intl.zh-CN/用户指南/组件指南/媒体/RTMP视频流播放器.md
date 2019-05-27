# RTMP视频流播放器 {#concept_tpj_p2l_gfb .concept}

RTMP视频流播放器是媒体组件的一种，支持自定义视频的url地址和类型，能够在大屏中添加视频播放器来播放您的视频。RTMP视频流播放器组件只支持rtmp协议的视频流。本文档为您介绍RTMP视频流播放器各配置项的含义，帮助您快速准确地使用RTMP视频流播放器组件。

## 样式 {#section_ycw_lxr_q2b .section}

-   **基础属性** 

    -   图表尺寸：组件的宽度和高度，单位为px。
    -   图表位置：组件在大屏中的位置，通过横纵坐标来定义，单位为px。
    -   其他：组件的旋转角度和透明度。
-   **视频流地址**：视频流的url地址。

    **说明：** 

    -   您需要使用rtmp协议的视频流。
    -   **样式**和**数据**中均可配置视频流的地址和类型，系统优先使用数据中的配置。
-   **视频流类型**：播放的视频流格式类型，可选：rtmp/mp4、rtmp/flv。
-   **静音播放**：勾选后，在预览或发布页面视频可静音播放；去勾选，视频正常播放声音。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21806/155894026812817_zh-CN.png)


## 数据 {#section_atz_kyr_q2b .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21806/155894026812818_zh-CN.png)

-   source: （可选） 视频流地址，与**视频流地址**配置项功能相同。如果同时配置，则以source中的内容为准。
-   type: （可选） 视频流类型，与**视频流类型**配置项功能相同。如果同时配置，则以type中的内容为准。

## 交互 {#section_y13_b3y_gfb .section}

此组件没有交互事件。

