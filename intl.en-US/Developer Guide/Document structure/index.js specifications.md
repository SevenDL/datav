# index.js specifications {#concept_bmf_nxl_q2b .concept}

This topic explains index.js specifications using an index.js template. For more information, see [widget examples](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/70446/cn_zh/1524462325165/index.js?spm=a2c4g.11186623.2.3.wQf3kR&file=index.js).

## Common functions {#section_hmn_4xl_q2b .section}

-   `render(array: data, object: config) || updateOptions(object: config)`

    The `render` function is the default rendering method. After a widget is initialized, the widget rendering logic is called. The input parameters are data and config, and the config parameter is optional. The `updateOptions` function receives the updated configuration items as parameters to change the rendering effect.

    -   Both render and updateOptions are rendering methods. If render supports config \(the second parameter\), updateOptions is optional.
    -   If the `updateOptions` function exists, updateOptions \(not `render`\) will receive the updated configuration items.
    -   Re-rendering must be supported. To ensure the same rendering effect, the values of data and config input must be the same input values.
    **Note:** If the `handler` function is set for the configuration items, this function receives the updated configuration items. You can set the `handler` function to improve the availability of the widgets with complex configuration items.

-   `emit(event_name, value)`

    With this function, you can set an event name and a global parameter using a widget in package.json. For other widgets that are in the same project as the preceding widget, you can obtain the value of the global parameter by calling the global parameter name using a colon \(:\) during data configuration.

    **Note:** The value of value must be an object and cannot be a value.

-   `resize(int: width, int: height)`

    This function is called to drag or resize a widget.

-   `clear()`

    This function is called to clear a widget.

-   `destroy()`

    This function is called to delete or remove a widget.

-   `require(*)`

    This function supports JavaScript and HTML.


