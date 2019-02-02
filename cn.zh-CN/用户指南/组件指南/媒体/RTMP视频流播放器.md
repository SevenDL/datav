# RTMP视频流播放器 {#concept_tpj_p2l_gfb .concept}

使用RTMP视频流播放器组件，可以在您的大屏项目中添加一个或多个RTMP视频流播放器组件，通过播放器在大屏上播放您想要的视频流。RTMP视频流播放器组件只支持rtmp协议的视频流。

## 样式 {#section_ycw_lxr_q2b .section}

-   **基础属性**

    -   图表尺寸：通过修改宽度和高度，调整组件的大小。
    -   图表位置：通过修改横坐标和纵坐标，改变组件在布局中的位置。
    -   其他：调整组件的旋转角度和透明度。
-   **视频流地址**：输入视频流具体的url网址。

    **说明：** 

    -   您需要使用rtmp协议的视频流。
    -   **样式**和**数据**中均可配置视频流的地址和类型。若两处都配置了，**数据**中的会覆盖掉**样式**中的。
-   **视频流类型**：选择播放的视频流格式类型。
    -   rtmp/mp4
    -   rtmp/flv
-   **静音播放**：勾选后，在预览或发布页面视频可静音播放；去勾选，视频正常播放声音。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21806/154907744512817_zh-CN.png)


## 数据 {#section_atz_kyr_q2b .section}

-   source: （可选） 视频流地址，与样式中的**视频流地址**功能相同。如果同时配置，则以source中的内容为准。
-   type: （可选） 视频流类型，与样式中的**视频流类型**功能相同。如果同时配置，则以type中的内容为准。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21806/154907744512818_zh-CN.png)

## 交互 {#section_y13_b3y_gfb .section}

此组件没有交互事件。

