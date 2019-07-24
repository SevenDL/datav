# 如何使用Tab列表控制组件显隐 {#concept_943895 .concept}

本文档以**Tab列表**控制**区域图**的显隐为例，为您介绍使用DataV节点编程功能控制组件显隐的方法。

本文档为您提供以下两种解决方案。

-   通过**触发器**设置触发条件控制组件的显示和隐藏，详情请参见下文的[通过触发器控制](#section_4vj_axh_w8p)。
-   通过**转换器**结合**组内轮播**功能控制组件的显示和隐藏，详情请参见下文的[通过转换器控制](#section_v4h_4bo_xx4)。

## 通过触发器控制 {#section_4vj_axh_w8p .section}

1.  参考[添加组件](../../../../cn.zh-CN/管理组件/添加组件.md#)，在可视化大屏编辑器页面搭建所需要的**Tab列表**和两个**区域图**组件。

    ![添加组件](images/50569_zh-CN.gif)

2.  单击大屏编辑页面右上角的**配置节点编程**图标。

    ![配置节点编程图标](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/763419/156396120952880_zh-CN.png)

3.  在节点编程配置页面，将左侧的**Tab列表**和两个**区域图**节点拖至画布中，并按照如下图所示的样式进行连线。

    ![连线](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/763419/156396120950570_zh-CN.png)

4.  添加触发器。

    连线中需要添加两个触发器，分别命名为**id=1**和**id=2**，如上图所示。具体操作方法请参见[配置节点编程](cn.zh-CN/节点编程使用说明/配置节点编程.md#)。

5.  配置触发器。
    1.  右键单击名称为**id=1**的触发器，选择**编辑**。
    2.  在触发器设置对话框的触发器脚本编辑区域，输入触发条件`return data.id == 1;`，单击**保存**。

        ![编辑触发器脚本1](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/763419/156396120950571_zh-CN.png)

    3.  使用同样的方式配置名称为**id=2**的触发器，输入触发条件`return data.id == 2;`。

        ![编辑触发器脚本2](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/763419/156396121050572_zh-CN.png)

        **说明：** 该触发条件下，实现的交互是**Tab列表**的参数`id=1`的情况下，一号区域图显示，二号区域图隐藏。

6.  触发器配置完成后，单击节点编程配置页面右上角的**应用**图标，将交互效果应用到大屏项目中。
7.  返回DataV编辑器页面，单击**预览**即可查看**Tab组件**控制**区域图**组件显隐的交互效果。

    ![组件显隐交互效果](images/50573_zh-CN.gif)


## 通过转换器控制 {#section_v4h_4bo_xx4 .section}

1.  在大屏项目的编辑器页面，搭建所需要的**Tab列表**和两个**区域图**组件。
2.  将两个**区域图**重叠放置，并全部选中，右键单击**成组**。

    ![成组](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/763419/156396121050611_zh-CN.png)

3.  单击成组的对象，在右侧的配置栏中，打开**组内对象轮播**开关，并将**基础设置**中的**触发方式**设置为**事件触发**。

    ![组内对象轮播](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/763419/156396121050613_zh-CN.png)

4.  单击大屏编辑页面右上角的**配置节点编程**图标。
5.  在节点编程配置页面，将左侧的**Tab列表**和**区域图组**节点拖至画布上，并按照如下图所示的样式连线。

    ![连线](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/763419/156396121050620_zh-CN.png)

6.  在连线中间添加一个转换器，并命名为**翻页**。
7.  配置转换器。
    1.  右键单击转换器，选择**编辑**。
    2.  在转换器设置对话框的转换器脚本编辑区域，输入如下脚本，单击**保存**。

        ``` {#codeblock_bz4_ye6_m7c}
        return {  
          index: data.id - 1 
        };
        ```

        ![编辑转化器脚本](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/763419/156396121050622_zh-CN.png)

8.  转换器配置完成后，单击节点编程配置页面右上角的**应用**图标，将交互效果应用到大屏项目中。
9.  返回DataV编辑器页面，单击**预览**即可查看**Tab组件**控制**区域图组**组内翻页，实现组件显隐的交互效果。

    ![组件显隐的交互效果](images/50623_zh-CN.gif)


