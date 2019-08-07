# package.json规范 {#concept_yhh_qcl_q2b .concept}

package.json文件是组件的配置文件。本文档为您介绍package.json文件的字段详情，您可以参考本文档的字段说明，根据自身需求，灵活修改package.json文件，自定义组件样式。

## 协议版本2规范示例 {#section_n4k_rcl_q2b .section}

**说明：** 请着重查看下述案例中的备注信息。

``` {#codeblock_axv_qib_lqu}
{
"name": "@leaf/pie-multi-radius-with-title",   
 //@命名空间/组件名 （命名空间即组件包名，必须添加，否则无法发布。）
"version": "0.1.5",                            //版本号。
"dependencies": {                             //依赖, 不包括datav:/com/依赖。
"bcore": "0.0.9",
"jquery": "2.1.4",                            //所有依赖的版本号必须锁死。
"lodash": "4.6.1"
},
"datav": {                                     //datav配置。
"cn_name": "带标题的多维饼图",                  //组件中文名。
"protocol": 2,                                //协议版本号。
"type": ["regular_pie"],                      //组件类型。
"view": {
    "width": 300,
    "height": 200,
    "minWidth": 100,
    "minHeight": 50
},
"icon": "",                                    //组件图标链接地址。
"apis": {                                      //组件接口，可以多个。
  "source": {                                  //接口名。
    "handler": "render",                       //处理接口返回的组件方法名。
    "description" : "多维度饼图接口",           //接口描述。
    "fields" : {                               //接口所需字段，可以多个。
      "x" : {                                  //字段名。
        "description" : "类目",                //字段描述。
        "type" : "string",                     //字段类型。
        "optional": true                       //可选字段。
      },
      "y" : {
        "description" : "值",
        "type" : "int"
      }
    }
  }
},
"config" : {                                 //组件配置，给编辑器识别用。
  "paxis" : {
    "type" : "group",                        //类型：组，详见<组件config配置说明>。
    "name" : "标签",
    "children" : {
      "dx" : {
        "type" : "text",                //类型：文本，详见<组件config配置说明>。
        "name" : "标签距中心",
        "default" : 220
      }
    }
  },
  "title" : {
    "type" : "group",
    "name" : "标题",
    "children" : {
      "value" : {
        "hasVisibility" : "true",
        "visible" : "true",
        "type" : "text",
        "name" : "标题名",
        "default" : "我是标题"
      },
      "font-size" : {
        "type" : "number",                 //类型：数字，详见<组件config配置说明>。
        "name" : "字体",
        "min" : 10,
        "default" : 32,
        "max" : 100
      },
      "text-align" : {
        "name" : "对齐方式",
        "type" : "select",                //类型：下拉框，详见<组件config配置说明>。
        "options" : [
          {"name" : "左对齐", "value" : "left"},
          {"name" : "右对齐", "value" : "right"},
          {"name" : "居中对齐", "value" : "center"}
        ],
        "default" : "center"
      },
      "color" : {
        "name" : "字体颜色",
        "type" : "color",                  //类型：颜色，详见<组件config配置说明>。
        "default" : "#fff"
      },
      "background-color" : {
        "name" : "背景",
        "type" : "color",
        "default" : "#000"
      }
    }
  }
},
"api_data":{                          //接口数据，可以多个。
  "source" : [                       //接口名，必须和apis中的接口名一致，限制6K。
    {"x": "普货", "y" : 5},
    {"x": "普货", "y" : 22},
    {"x": "泡货", "y" : 22},
    {"x": "设备", "y" : 14},
    {"x": "矿产", "y" : 15},
    {"x": "钢铁", "y" : 15},
    {"x": "建材", "y" : 12},
    {"x": "食品", "y" : 12},
    {"x": "粮食", "y" : 28}
  ],
},
"events": {                           //全局参数事件配置。
  "event-name": {                     //事件名。               
  "description": "事件描述",          //事件描述。
    "fields": {                      //字段，可以多个。
      "value": {                     //字段名。
        "description": "值描述"       //字段描述。
      }
    }
  }
},
"publicHandler": {
    "show": {
        "name": "显示",
        "description"： "描述",
        "type": "object",        // 可以为object、array、null和any，any表示任意类型。
        "fields": {
            "data": {
                "name": "数据",
                "type": "array",
                "children": {
                    ...
                }
            }
        }
    }
 },
}
}
```

## 配置项config字段说明 {#section_bxw_vcl_q2b .section}

config配置用来说明组件有哪些配置。这些配置既用于传给组件，也用于说明编辑器的选项。

config配置有以下两个要求。

-   包含组件默认配置。
-   描述清楚配置的输入规范，以便编辑器进行识别。

config配置中的handler和type字段说明如下。

-   handler字段
    -   在 config的任意配置项中配置了handler后，意味着该配置项发生改变之后，该配置项及所有子配置项将以参数的形式传至定义函数名的函数。
    -   改变该配置项不会将新配置传至默认的render方法中，如果需要在render或其他函数中用到该配置项，可在定义函数中将配置与this.config合并。

        ``` {#codeblock_k7o_51t_nna}
        "config": {
        "example": {
          "type": "group",
          "name": "图形属性",
          "handler": "updateBar",            //自定义函数名。
          "children": {
            "_innerRadius": {
              "type": "number",
              "name": "内半径",
              "default": 0.4,
              "range": [
                0,
                1
              ]
            }
          }
        }
        }
        ```

-   type字段

    **说明：** 不同type类型会展示不同的编辑器UI，合理使用type类型和配置项归类，可以极大提高组件质量与用户体验。

    |类型|说明|
    |:-|:-|
    |group|配置项组，可包裹多个子配置项（建议多个同类元素配置项归于一个group）。|
    |text|文字。|
    |number|数值。|
    |select|下拉选择框。|
    |search|下拉搜索框。|
    |color|颜色。|
    |multicolor|渐变颜色（可选单色或渐变色）。|
    |image|图片。|
    |array|数组（适用于多个系列时或多个颜色循环配色等）。|
    |hidden|隐藏配置项（编辑器不会配置此字段）。|
    |boolean|布尔值。|
    |radio|单选框。|
    |percent|百分比值。|
    |imageSelect|装饰元素。|

    -   `type : group` 

        ``` {#codeblock_uj8_wl9_8t6}
        "margin": {
        "type" : "group",                                                
        "name" : "标签",                           
        "children" : {    
        }
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |children|组内元素|否|没填时，组为空。|

    -   `type : text` 

        ``` {#codeblock_ee7_8gu_1gm}
        {
        "type" : "text",                                                
        "name" : "标题",                           
        "default": "我是标题"
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认显示值|否|没填时为空。|

    -   `type : number` 

        ``` {#codeblock_etv_hjt_rgd}
        {
        "type" : "number",                                                
        "name" : "字号",                        
        "default": 22,
        "min": 10,            
        "max": 55,
        "range": [10, 55],
        "range": {
        "min" : 10,
        "max" : 55
        }
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认显示值|不涉及|没填时为16。|
        |min|最小值|否|min\\range\[0\]\\range.min三者有其一就设置最小值成功，都没有时退化为text，不保证运行正确。|
        |max|最大值|否|min\\range\[1\]\\range.max三者有其一就设置最大值成功，都没有时退化为text，不保证运行正确。|
        |range|取值区间|否|可以为数组\[10, 55\]，也可以为对象\{min: 10, max: 55\}，与min和max都没有时，退化为 text，不保证运行正确。|

        **说明：** 有最大或最小值时，UI 进化为 slider 拖动条。

    -   `type : select` 

        ``` {#codeblock_utw_k9f_t9d}
        {
        "name" : "对齐方式",
        "type" : "select", 
        "options" : [
         {"name" : "左对齐", "value" : "left"},
         {"name" : "右对齐", "value" : "right"},
         {"name" : "居中对齐", "value" : "center"}
         ],
        "default" : "center"
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认显示值|否|没填时为options\[0\]。|
        |options|下拉框选择|是|数组型 \[\{name: ‘’ ,value: ‘’\}\]，没有时退化为text。|

    -   `type : search` 

        ``` {#codeblock_3c7_beu_8l0}
        {
        "name": "字体",
        "type": "search",
        "default": "Microsoft Yahei",
        "range": [
        {
          "微软雅黑": "Microsoft Yahei"
        },
        {
          "宋体": "SimSun"
        },
        {
          "黑体": "SimHei"
        },
        {
          "隶书": "LiSu"
        },
        {
          "幼圆": "YouYuan"
        },
        "tahoma",
        "arial",
        "sans-serif"
        ],
        "description": "请选择您系统有的字体,如果您系统无此字体,标题将会显示默认字体"
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认显示值|否|没填时为options\[0\]。|
        |range|下拉框选择|是|数组型\[\{name: ‘’ ,value: ‘’\}\]，也可以为\[\{key: value\}\]型，也可以只有\[value\]， 没有时退化为text。|

    -   `type : color` 

        ``` {#codeblock_ooy_a70_7p8}
        {
        "name" : "字体颜色",
        "type" : "color", 
        "default" : "#fff"
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认显示值|否|没填时为\#000。|

    -   `type : multicolor` 

        ``` {#codeblock_7vy_lx0_066}
        {
        "name" : "渐变颜色",
        "type" : "multicolor", 
        "default" : {
        "style": "single",
        "value": "#ccc",
        "from": "#000",
        "to": "#fff",
        "angle": 0
        }
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认显示值|是|style为single或double，value为single单值，from，to，angle代表当style为double时渐变的角度。|

        当style为single时，返回的真实值如下。

        ``` {#codeblock_d65_6j1_ac2}
        {
        "style": "single",
        "value": "#xxx"
        }
        ```

        当style为double时，返回的真实值如下。

        ``` {#codeblock_576_vo7_t0j}
        {
        "style": "double",
        "from": "#xxx",
        "to": "#xxx",
        "angle": 90
        }
        ```

    -   `type : image` 

        ``` {#codeblock_ncz_81q_li9}
        {
        "name" : "背景图",
        "type" : "image",
        "default": "http://datav.oss-cn-hangzhou.aliyuncs.com/uploads/images/c4ba3c6518c1997f4baa612a600c3fbe.png"
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认显示值|否|没填时为空，无图片。|

        **说明：** 若图片链接为本地静态文件，需将图片文件放至当前组件目录resources文件夹下，如./resources/xxxx.png。

    -   `type : array` 

        ``` {#codeblock_50q_6hl_w55}
        {
        "name" : "数据系列",
        "type" : "array",
        "default": [{"name": "系列一", value: "进港"},{"name": "系列二", value: "出港"}]
        "child": {
        "name" : "系列<%=i+1%>",
        "type" : "object",
        "child": {
          "name": {
            "name" : "系列值",
            "type" : "text",
            "default": "系列"
          },
          "value": {
            "name" : "系列名",
            "type" : "text",
            "default": ""
          }
        }
        }
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认值|是|对象数组，对象的属性应与child字段中定义的字段名一致。|
        |child|对象名|是|该字段内的type应设为object。|
        |child|对象属性|是|object 字段下的child用于定义对象属性及其默认值。|

        **说明：** 数据系列的default值必须为一个对象数组，数组内对象中的属性必须在child字段中逐一进行定义，并设置属性值的显示名，类型及默认值。

    -   `type : hidden` 

        ``` {#codeblock_084_0dq_oxy}
        {
        "type" : "hidden",
        "name": "值",
        "default": 22
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|编辑器不会配置此字段。|
        |name|显示名|是|无。|
        |default|默认值|否|设置默认不显示的值，但是会作为config传给方法。|

    -   `type : boolean` 

        ``` {#codeblock_r5o_g5q_fpi}
        {
        "type" : "boolean",
        "name" : "显示",
        "default": true
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认值|否|没填时为false。|

    -   `type : radio` 

        ``` {#codeblock_9ja_okn_v6g}
        {
          "name":"字体粗细",
          "type":"radio",
          "default":1,
          "list":[  
            {  
              "name":"正常",
              "value":1
            },
            {  
              "name":"加粗",
              "value":2
            }
          ]
         }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |list|选择列表|是|对象数组，含name和value字段。|
        |default|默认值|否|不填时默认没有选中项。|

    -   `type : percent` 

        ``` {#codeblock_kxn_5jl_0fd}
        "percent": {
        "type": "percent",
        "name": "百分比值",
        "default": 20
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|无。|
        |default|默认值|否|不填时值为空。|

    -   `type : imageSelect` 

        ``` {#codeblock_l5a_krn_4mx}
        "imageSelect": 
        {
        "name": "装饰元素",
        "type": "imageSelect",
        "default": "gif1",
        "range": [
        {
        "name": "gif1",
        "value": "gif1",
        "url": "https://img.alicdn.com/tps/TB1tFMtPXXXXXXyXpXXXXXXXXXX-1920-1080.gif"
        },
        {
        "name": "gif2",
        "value": "gif2",
        "url": "https://img.alicdn.com/tps/TB1Pg3pPXXXXXcxXpXXXXXXXXXX-1920-1080.gif"
        }
        ]
        }
        ```

        |字段名|含义|是否必选|备注|
        |:--|:-|:---|:-|
        |type|类型|是|无。|
        |name|显示名|是|不填时使用key名作为显示名，例如margin。|
        |default|默认值|否|不填时值为options\[0\]。|
        |range|下拉框选择|是|数组型\[\{name:'',value: '',url: ''\}\]。|


## 自定义配置项的显示与隐藏 {#section_njy_kwl_q2b .section}

您可以使用show字段，来对自定义配置项进行显示和隐藏。

``` {#codeblock_g97_73j_t0r}
{
"xAxis": {
    "type": "group",
    "name": "x轴",
    "children": {
        "show": { //在x轴右侧展示一个显示的点选框，但其实不含兄弟属性是否显示的功能。
             "type": "boolean",
             "name": "显示",
             "default": true
        },
        "color": {
            "type": "color",
            "name": "颜色",
            "default": "#ccc",
            "show": [            //单个属性是否显示的功能。
                ["show", "$eq", true]     //表示color要显示的情况是：我的兄弟show = true的时候我才显示。
            ]
        }
    }
}
}
```

## apis字段与api\_data字段 {#section_cdp_nwl_q2b .section}

-   apis字段

    该字段定义了组件接口名，以及该接口所需的字段。接口和字段均可为多个（详情请参见注释）。

    ``` {#codeblock_tlc_pl0_yma}
    "apis": {                               //组件接口，可以多个。
    "source": {                             //接口名。
    "handler": "render",                     //处理接口返回的组件方法名。
    "description" : "多维度饼图接口",          //接口描述。
    "fields" : {                             //接口所需字段，可以多个。
     "x" : {                                 //字段名。
       "description" : "类目",                //字段描述。
       "type" : "string",                     //字段类型。
       "optional": true                       //可选字段。
     },
     "y" : {
       "description" : "值",
       "type" : "int"
     }
    }
    }，
    "source2":{
          ...                                     //接口2。
    }
    }
    ```

-   api\_data字段

    该字段定义了接口数据，可以多个。接口名必须和apis中的接口名一致，限制为 6KB（详情请参见注释）。

    ``` {#codeblock_4lc_u7c_w79}
    "api_data":{                          //接口数据，可以多个。
      "source" : [                       //接口名，必须和apis字段中的接口名一致，限制6K。
        {"x": "普货", "y" : 5},
        {"x": "普货", "y" : 22},
        {"x": "泡货", "y" : 22},
        {"x": "设备", "y" : 14},
        {"x": "矿产", "y" : 15},
        {"x": "钢铁", "y" : 15},
        {"x": "建材", "y" : 12},
        {"x": "食品", "y" : 12},
        {"x": "粮食", "y" : 28}
      ],
    },
    ```


## events交互事件规范 {#section_gzl_dxl_q2b .section}

DataV的交互事件由`emit`（组件代码中触发`emit`）和events描述（package.json的事件描述）共同与产品沟通而成。

-   events字段描述

    events字段在datav字段下，与config等字段同级，这个字段定义了交互事件的事件名，描述以及变量名等（详情请参见注释）。

    ``` {#codeblock_rfg_2fs_cib}
    package.json
    {
    "events": {                 
        "click-me": {                                //自定义的事件名。
            "description": "点击触发事件",           //事件描述字段可描述该事件的具体作用。
            "fields": {                            //可定义多个变量名及其描述信息。
                "value": {                        //字段名，任意，并且在产品中可以由用户修改。
                    "description": "点击值" 
                }
            }
        }
    }
    }
    ```

-   `emit`触发

    `emit`方法作为一个基础类方法，会将事件名及需要的数据作为参数抛出，其他组件即可通过变量名获取到该组件的参数值（详情请参见注释）。

    ``` {#codeblock_w3e_ahy_evb}
    index.js
    render: function () {
        this.container.on('click', () => {
            this.emit('click-me', data)            // data必须为一个对象，而不是一个简单值，属性名即为变量名。
        })
    }
    ```


## type字段 {#section_nsx_3xl_q2b .section}

type字段定义了该组件的组件类型（详情请参见注释）。

``` {#codeblock_uti_806_mtc}
type: ["regular_bar", ...]  //一个组件可以属于多个组，多个组件类型以下划线分隔："type1_type2"。
    {                      // 常用组件类型。
      regular: "常规图表",
      map: "地图", 
      figure: '指标', 
      network: "关系网络", 
      text: "文字", 
      decorate: "辅助图形"
    }
```

## publicHandler字段 {#section_cik_ygx_wj1 .section}

DataV的行为事件定义是通过publicHandler注册而成，示例如下。

``` {#codeblock_4ga_f7i_grr}
"publicHandler": {
        "show": {
            "name": "显示",
            "description"： "描述",
            "type": "object",    // 可以为object、array、null和any，any表示任意类型。
            "fields": {
                "data": {
                    "name": "数据",
                    "type": "array",
                    "children": {
                        ...
                    }
                }
            }
        }
     },
```

|字段名|含义|是否必选|备注|
|---|--|----|--|
|name|事件名|是|在节点编程配置中使用。|
|description|事件描述|否|无严格的字数限制。|
|type|事件第一入参|否|可选，包含array、object、null和any。 any表示任意类型，如果缺省值有fields ，默认为object，如果没fields， 默认为null。

 |
|fields|字段|否|无。|
|fields.name|字段名|是|无。|
|fields.description|字段描述|否|无。|
|fields.type|字段类型|是|可选，包括number、string、boolean、object和array。|
|fields.children|子节点|否|当fields.type为object或array时需要children字段。|
|fields.default|默认值|否|当fields.type为number、string或boolean时，需要填写默认值。|
|fields.optional|是否可选|否|可选，为boolean类型。|

