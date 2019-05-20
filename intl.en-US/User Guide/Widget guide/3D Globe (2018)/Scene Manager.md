# Scene Manager {#concept_fvl_2kv_rfb .concept}

Scene Manager enables you to view the different parts of a globe by rotating and zooming the camera.

## Style {#section_p4j_trq_gfb .section}

-   **Enable**: Select the Enable check box to enable the scene manager. Clear the check box to disable the scene manager.
-   **Carousel Mode**: Click the drop-down list and select the carousel mode as needed.
    -   **Play once.**
    -   **Loop.**
-   **Duration**: Drag the slider or enter a number manually to adjust the duration of the animation for each scene. The value is from 0 to 30000. The unit is in milliseconds. If the values of the duration properties in the data source are specified, then the value of the Duration property in the Style pane is not applicable.
-   **Delay**: Drag the slider or enter a number manually to adjust the interval between the animations for scenes. The value is from 0 to 30000. The unit is in milliseconds. If the values of the delay properties in the data source are specified, then the value of the Delay property in the Style pane is not applicable.
-   **Callback ID**: Sets the callback ID of the component. The value of a callback ID \(similar to a parameter variable\) is passed to other components when the animation for a scene ends. A callback ID specifies the field that is used to implement filter interactions among components. The field must be contained in the data source.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41689/155832240721625_en-US.png)

## Data {#section_w1h_wqr_gfb .section}

-   name: Specifies the name of the scene.
-   position: Specifies the coordinate of the scene, the field of view of the camera, and the distance to the camera. The position property includes four properties: fov \(camera field of view\), lat \(latitude\), lng \(longitude\), and distance \(camera distance\).
-   duration: Specifies the duration of the animation for the scene.
-   delay: Specifies the time interval between animations for the scenes.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41689/155832240821629_en-US.png)

## Interaction {#section_y13_b3y_gfb .section}

**Enable**: Select the Enable check box to enable interactions among the components. You can configure interactions in Scene Manager to pass the value of a callback ID when a scene ends. The default callback ID is the id property in the data source. For more information, see [Configurations for component callback IDs](../../../../intl.en-US/Best Practices/Configure callback IDs for ticker boards.md#).

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/41689/155832240821630_en-US.png)

