# Word cloud {#concept_qvd_xgb_kfb .concept}

The word cloud widget allows you to customize the style and shape of the word clouds and the data values as needed.

## Style {#section_p4j_trq_gfb .section}

-   **Basic Attributes**

    -   **Size**: Set the size of the widget by adjusting its width and height.
    -   **Position**: Set the position of the widget by adjusting its abscissa and ordinate.
    -   **Others**: Set the rotation angle and opacity of the widget.
-   **Global Settings**
    -   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
    -   **Max Font Size**: To set the maximum font size of the displayed text, enter a value or drag the slider.
    -   **Min Font Size**: To set the minimum font size of the displayed text, enter a value or drag the slider.
-   **Shape**: To display the shape of the word cloud, click the **Eye** icon.

    -   **Image**: To delete the image, click the **Delete** icon in the dashed line box. You can enter an image URL or drag an existing image to the dashed line box from your local server.
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22637/155808354213357_en-US.png)

-   **Series**: To add or delete a series, click **+** or click the **Trash** icon.

    -   **Series Color**: To change the font color of the text of each series, see [Color picker](intl.en-US/User Guide/Manage widgets/Set widget styles/Configure item description.md#section_kdw_vj4_t2b).
    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22637/155808354213358_en-US.png)


## Data {#section_w1h_wqr_gfb .section}

name: The name displayed in the widget.

value: The weight of a name. This field determines the font size of the text.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/22637/155808354213359_en-US.png)

**Note:** The widget sorts the data and then renders the [series](#) style according to the data sequence.

The following is an example:

```

[
{
"name": "1",
"value": 321
},
{
"name": "2",
"value": 21
},
{
"name": "3",
"value": 2
},
{
"name": "4",
"value": 1
}
]

```

The configuration items are as follows: series 1:"red", series 2:"blue", series 3:"yellow".

The rendering result is as follows: name:1 =\> "red", name:2 =\> "blue",name:3 =\> "yellow",name:4 =\> "red".

## Interaction {#section_y13_b3y_gfb .section}

This widget is not connected to any events yet.

