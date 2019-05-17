# Carousel images {#concept_ncq_q2l_gfb .concept}

You can add one or more carousel images to a project to display the image or images in rotation.

## Style {#section_ycw_lxr_q2b .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Global Settings**

    -   **Font Family**: Font of the displayed text. Only a font that is installed in your system can be displayed accurately. If the selected font is not installed in your system, the default font is displayed.
    -   **Font Size**: To change the font size of the displayed text, enter a value or drag the slider. The value range is from 10 to 100.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21807/155808423812873_en-US.png)

-   **Animation**

    -   **Interval**: To change the time interval between the display of two images, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Speed**: To change the transition speed of displaying images, enter a value, or click **+** or **–**. The unit is milliseconds.
    -   **Special Effects**: animation effect.
        -   Scroll horizontally
        -   Scroll vertically
        -   Fade in and fade out
        -   Mosaic
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21807/155808423812874_en-US.png)

-   **Image**

    -   **Default Image**: You can enter an image URL or drag an existing image to the dashed line box. You can click the **Delete** icon to delete an image.
    -   **Fill Type**: To set the fill type, click the drop-down arrow and select the target type.
        -   Stretch to fill the container
        -   Fill container
        -   Center
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21807/155808423812875_en-US.png)

-   **Description**: To display the image description, click the **Eye** icon.

    -   **Background Color**
        -   **Fill Style**: To set the fill color type, click the drop-down arrow and select the target type.
            -   Solid
            -   Gradient
        -   **Start Color**: To change the start color of the gradient colors, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **End Color**: To change the end color of the gradient colors, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
        -   **Angle**: You can change the gradient angle as needed. The setting takes effect only when **Fill Style** is set to **Gradient**. The gradient angle cannot be set when **Fill Style** is set to **Solid**.
    -   **Color**: To set the font color of the displayed text, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   **Font Weight**: To change the font weight of the displayed text, click the drop-down arrow and select the target font.
    -   **Width**: To change the width of the description bar, enter a value, or click **+** or **–**. The unit is %.
    -   **Height**: To change the height of the description bar, enter a value, or click **+** or **–**. The unit is %.
    -   **Top**: To adjust the spacing between the description bar and the top border, enter a value, or click **+** or **–**.
    -   **Bottom**: To adjust the spacing between the description bar and the top border, enter a value, or click **+** or **–**.
    -   **Align**: To change the position of the description text in the description bar, click the drop-down arrow and select the target position.
        -   Left
        -   Center
        -   Right
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21807/155808423812876_en-US.png)

-   **Pagination Bullets**: To display the pagination bullets, click the **Eye** icon.

    -   Inactive color: To change the color of the pagination bullets corresponding to the images that are not displayed, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    -   Active color: To change the color of the pagination bullet corresponding to the displayed image, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21807/155808423812877_en-US.png)


## Data {#section_atz_kyr_q2b .section}

-   url: image URL, which corresponds to the URL of the **Default Image** in the configuration pane. If you have set the URL both in the configuration and data panes, the value of url takes effect.

    **Note:** Cross-domain settings are required for this image. If you do not specify the HTTP, for example, //img.alicdn.com/tps/TB1PH6EPXXXXXXbaFXXXXXXXXXX-4001-2251.png, the system will send a request to the image according to the access HTTP of the project.

-   description: \(optional\) image description. You can add a pair of HTML **a** tags to the value of this field.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21807/155808423812861_en-US.png)

## Interaction {#section_y13_b3y_gfb .section}

This widget is not connected to any events yet.

