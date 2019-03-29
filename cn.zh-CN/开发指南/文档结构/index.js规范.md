# index.js规范 {#concept_bmf_nxl_q2b .concept}

模板案例：详情请参见[example组件](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/64800/cn_zh/1553828656284/index.js)。

## 常用函数 {#section_hmn_4xl_q2b .section}

-   `render(array: data, object: config) || updateOptions(object: config)`

    `render`为默认渲染方法，当组件被初始化后，组件渲染逻辑被调用。入参为数据和配置，其中配置为可选参数。`updateOptions`接受更新后的配置项作为参数，改变界面渲染效果。

    -   两者皆为渲染方法，如果 render 支持第二个参数config，则 updateOptions 不是必须的。
    -   当`updateOptions`函数存在时，改变配置项后该函数将收到更新后的配置项，而不是`render`。
    -   渲染需要能够支持重渲染，保证一样的数据、配置输入，才能渲染出一样的效果。
    **说明：** 当配置项配置了`handler`时，配置项改变时该函数将收到新配置项。对于一些配置项复杂的组件，设置`handler`是一个提高组件可读性的好方法。

-   `emit(event_name, value)`

    此方法可以使用组件在package.json中设置的事件名，并设置一个全局参数。组件所在大屏中的其他组件，可在数据配置中使用冒号调用此参数名获得此参数的值。

    **说明：** value 必须是对象，而不是基础类型的值。

-   `resize(int: width, int: height)`

    缩放，当组件被拖拽、缩放时被调用。

-   `clear()`

    清理，当组件被清理时被调用。

-   `destroy()`

    销毁，当组件被销毁时调用。

-   `require(*)`

    支持 js、 html。


