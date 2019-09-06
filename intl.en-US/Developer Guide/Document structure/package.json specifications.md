# package.json specifications {#concept_yhh_qcl_q2b .concept}

## Specifications example of protocol version 2 {#section_n4k_rcl_q2b .section}

**Note:** Pay attention to the notes in the following example:

```
{
"name": "@leaf/pie-multi-radius-with-title",   
 //@Namespace/Widget package name (The namespace is the name of a widget package. A widget package cannot be published without a namespace.)
"version": "0.1.5",                            //Version number
"dependencies": {                              //Dependencies, excluding datav:/com/another datav widget
"bcore": "0.0.9",
"jquery": "2.1.4",                             //All the dependent version numbers must be locked.
"lodash": "4.6.1"
},
"datav": {                                     //DataV configuration
"cn_name": "doughnut chart with title",                   //Chinese name of a widget
"protocol": 2,                                 //Protocol version number
"type": ["regular_pie"],                       //Widget type
"view": {
    "width": 300,
    "height": 200,
    "minWidth": 100,
    "minHeight": 50
},
"icon": "",                                       //Icon URL of a widget
"apis": {                                      //Widget API. Multiple APIs are supported.
  "source": {                                  //API name
    "handler": "render",                       //Processes the widget function name returned from an API.
    "description" : "doughnut chart API",            //API description
    "fields" : {                               //Fields required by an API. Multiple fields are supported.
      "x" : {                                  //Field name
        "description" : "category",                 //Field description
        "type" : "string",                     //Field type
        "optional": true                       //Optional field
      },
      "y" : {
        "description" : "value",
        "type" : "int"
      }
    }
  }
},
"config" : {                                 //Widget configuration, which is identified by the Editor
  "paxis" : {
    "type" : "group",                        //Type:group. For more information, see <Description of the config field>.
    "name" : "label",
    "children" : {
      "dx" : {
        "type" : "text",                //Type:text. For more information, see <Description of the config field>.
        "name" : "distance from label to center",
        "default" : 220
      }
    }
  },
  "title" : {
    "type" : "group",
    "name" : "title",
    "children" : {
      "value" : {
        "hasVisibility" : "true",
        "visible" : "true",
        "type" : "text",
        "name" : "title",
        "default" : "This is title."
      },
      "font-size" : {
        "type" : "number",                 //Type:number. For more information, see <Description of the config field>.
        "name" : "font",
        "min" : 10,
        "default" : 32,
        "max" : 100
      },
      "text-align" : {
        "name" : "alignment",
        "type" : "select",                //Type:drop-down list. For more information, see <Description of the config field>.
        "options" : [
          {"name" : "left aligned", "value" : "left"},
          {"name" : "right aligned", "value" : "right"},
          {"name" : "centered", "value" : "center"}
        ],
        "default" : "center"
      },
      "color" : {
        "name" : "font color",
        "type" : "color",                  //Type:color. For more information, see <Description of the config field>.
        "default" : "#fff"
      },
      "background-color" : {
        "name" : "background",
        "type" : "color",
        "default" : "#000"
      }
    }
  }
},
"api_data":{                          //API data. Multiple APIs are supported.
  "source" : [                       //API name, which must the same as that in the apis field. The recommended data size is within 6 KB.
    {"x": "cargo", "y" : 5},
    {"x": "cargo", "y" : 22},
    {"x": "light goods", "y" : 22},
    {"x": "device", "y" : 14},
    {"x": "mineral", "y" : 15},
    {"x": "metal", "y" : 15},
    {"x": "building material", "y" : 12},
    {"x": "food", "y" : 12},
    {"x": "grain", "y" : 28}
  ],
},
"events": {                           //Global parameter (event configuration)
  "event-name": {                     //Event name               
  "description": "event description",        //Event description
    "fields": {                      //Field. Multiple fields are supported.
      "value": {                     //Field name
        "description": "value description"       //Field description
      }
    }
  }
}
}
}
```

## Description of the config field {#section_bxw_vcl_q2b .section}

The config field describes the configuration items of a widget. The configuration items can be transferred to a widget or be used to describe the options of the Editor.

The following requirements must be met to set the config field:

-   The default settings of a widget must be included.
-   The input specifications must be clearly described for the Editor to identify.

-   handler field in the configuration items
    -   If you have set handler in a configuration item of config, when the configuration item is changed, both the configuration item and the items contained in this configuration item are transferred to the specified custom function in handler.

    -   Changes of this configuration item will not be transferred to the default render function. To use this configuration item in render or other functions, combine the configuration and this.config in the custom function.

        ```
        "config": {
        "example": {
          "type": "group",
          "name": "chart property",
          "handler": "updateBar",            //Custom function name
          "children": {
            "_innerRadius": {
              "type": "number",
              "name": "inner radius",
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

-   type field in the configuration items

    **Note:** Different Editor UIs are displayed according to different types. You can improve the widget quality and user experience by using the proper types and configuration items.

    |Type|Description|
    |:---|:----------|
    |group|Configuration item group, which can contain multiple configuration items. We recommend that you place elements of the same type into the same group.|
    |text|Text|
    |number|Value|
    |select|Drop-down list|
    |search|Combo box|
    |color|Color|
    |multicolor|Gradient color \(You can select a solid color or multiple colors as gradient colors.\)|
    |image|Image|
    |array|Array \(An array is used for multiple series and color cycling.\)|
    |hidden|Hidden configuration item \(The Editor does not set hidden configuration items.\)|
    |boolean|Boolean value|
    |radio|Check box|
    |percent|Numerical value|
    |imageSelect|Decorative elements|

    -   type:group

        ```
        "margin": {
        "type" : "group",                                                
        "name" : "label",                           
        "children" : {    
        }
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |children|Elements in a group|No|If this field contains no data, the group is empty.|

    -   type:text

        ```
        {
        "type" : "text",                                                
        "name" : "title",                           
        "default": "This is title."
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default display value|No|If this field contains no data, the display value is empty.|

    -   **type:number**

        ```
        {
        "type" : "number",                                                
        "name" : "font size",                        
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

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default display value|N/A|If this field contains no data, 16 is displayed.|
        |min|Minimum value|No|If one of the min, range\[0\], and range.min fields is set, the minimum value is successfully set. If the min, range\[0\], and range.min fields are not set, the value of type is set to text, and proper program running cannot be ensured.|
        |max|Maximum value|No|If one of the min, range\[1\], and range.max fields is set, the maximum value is successfully set. If the min, range\[1\], and range.max fields are not set, the value of type is set to text, and proper program running cannot be ensured.|
        |range|Value range|No|This field can be an array \(for example, \[10, 55\]\) or an object \(for example, \{min: 10, max: 55\}\). If the range, min, and max fields are not set, the value of type is set to text, and proper program running cannot be ensured.|

        **Note:** If a field has a maximum value or a minimum value, a slider is displayed on the UI.

    -   type:select

        ```
        {
        "name" : "alignment",
        "type" : "select", 
        "options" : [
         {"name" : "left aligned", "value" : "left"},
         {"name" : "right aligned", "value" : "right"},
         {"name" : "centered", "value" : "center"}
         ],
        "default" : "center"
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default display value|No|If this field contains no data, options\[0\] is displayed.|
        |options|Options in a drop-down list|Yes|This field is an array, for example, \[\{name: '' ,value: ''\}\]. If this field is not set, the value of type is set to text.|

    -   type:search

        ```
        {
        "name": "font",
        "type": "search",
        "default": "Microsoft Yahei",
        "range": [
        {
          "Microsoft Yahei": "Microsoft Yahei"
        },
        {
          "SimSun": "SimSun"
        },
        {
          "SimHei": "SimHei"
        },
        {
          "LiSu": "LiSu"
        },
        {
          "YouYuan": "YouYuan"
        },
        "tahoma",
        "arial",
        "sans-serif"
        ],
        "description": "Select a font that is already installed on your system. If your system does not have this font, the default font is used for the title."
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default display value|No|If this field contains no data, options\[0\] is displayed.|
        |range|Options in a drop-down list|Yes|This field can be in one of the following formats: \[\{name: '' ,value: ''\}\] \(an array\), \[\{key: value\}\], and \[value\]. If this field is not set, the value of type is set to text.|

    -   type:color

        ```
        {
        "name" : "font color",
        "type" : "color", 
        "default" : "#fff"
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default display value|No|If this field contains no data, \#000 is displayed.|

    -   type:multicolor

        ```
        {
        "name" : "gradient color",
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

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default display value|Yes|The value of style is single or double, and the value of value is single. The values of the from, to, and angle fields indicate the gradient range when the style field is set to double.|

        If style is set to single, the following actual data value is displayed:

        ```
        {
        "style": "single",
        "value": "#xxx"
        }
        ```

        If style is set to double, the following actual data value is displayed:

        ```
        {
        "style": "double",
        "from": "#xxx",
        "to": "#xxx",
        "angle": 90
        }
        ```

    -   type:image

        ```
        {
        "name" : "background image",
        "type" : "image",
        "default": "http://datav.oss-cn-hangzhou.aliyuncs.com/uploads/images/c4ba3c6518c1997f4baa612a600c3fbe.png"
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default display value|No|If this field contains no data, no image is displayed.|

        **Note:** If the image is a local static file, place the file into the resources directory of the widget, for example, ./resources/xxxx.png.

    -   type:array

        ```
        {
        "name" : "series",
        "type" : "array",
        "default": [{"name": "series 1", value: "arrival"},{"name": "series 2", value: "departure"}]
        "child": {
        "name" : "series<%=i+1%>",
        "type" : "object",
        "child": {
          "name": {
            "name" : "series value",
            "type" : "text",
            "default": "series"
          },
          "value": {
            "name" : "series name",
            "type" : "text",
            "default": ""
          }
        }
        }
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default value|Yes|Object array. The property of the object must be the same as the field name specified in the child field.|
        |child|Object name|Yes|The type field must be set to an object.|
        |child|Object property|Yes|The child field is used to define the object property and the default value.|

        **Note:** The default value of a series must be an object array. The property of the object in the array must be defined in child, and the display name, type, and default value of the object property must be set.

    -   type:hidden

        ```
        {
        "type" : "hidden",
        "name": "value",
        "default": 22
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|The Editor does not set this field.|
        |name|Display name|Yes|N/A|
        |default|Default value|No|The value is not displayed by default, but is transferred to a function.|

    -   type:boolean

        ```
        {
        "type" : "boolean",
        "name" : "display",
        "default": true
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default value|No|If this field contains no data, false is displayed.|

    -   type:radio

        ```
        {
          "name":"font weight",
          "type":"radio",
          "default":1,
          "list":[  
            {  
              "name":"normal",
              "value":1
            },
            {  
              "name":"bold",
              "value":2
            }
          ]
         }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |list|Drop-down list|Yes|An object array that contains the name and value fields|
        |default|Default value|No|If this field is not set, the default value is empty.|

    -   type:percent

        ```
        "percent": {
        "type": "percent",
        "name": "numerical value",
        "default": 20
        }
        ```

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|N/A|
        |default|Default value|No|If this field contains no data, the default value is empty.|

    -   type: imageSelect

        ```
        "imageSelect": 
        {
        "name": "decorative element",
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

        |Field name|Description|Required or not|Remarks|
        |:---------|:----------|:--------------|:------|
        |type|Type|Yes|N/A|
        |name|Display name|Yes|If this field contains no data, a key \(for example, margin\) is used as the display name.|
        |default|Default value|No|If this field contains no data, options\[0\] is displayed.|
        |range|Options in a drop-down list|Yes|This field is an array, for example, \[\{name:'',value: '',url: ''\}\].|


## Custom configuration item display and hiding {#section_njy_kwl_q2b .section}

This section describes how to use show to display or hide a custom configuration item.

```
{
"xAxis": {
    "type": "group",
    "name": "x-axis",
    "children": {
        "show": { //Displays a check box on the right side of the x-axis. This check box does not determine whether a similar property is displayed.
             "type": "boolean",
             "name": "display",
             "default": true
        },
        "color": {
            "type": "color",
            "name": "color",
            "default": "#ccc",
            "show": [            //Determines whether to display a property.
                ["show", "$eq", true]     //Condition under which the color is displayed: The color is displayed only when the show filed of a similar property is set to true.
            ]
        }
    }
}
}
```

## apis and api\_data fields {#section_cdp_nwl_q2b .section}

-   apis field

    This field defines the name of a widget API and the fields required by the API. Multiple APIs and fields are supported. For more information, see the notes in the preceding example.

    ```
    "apis": {                               //Widget API. Multiple APIs are supported.
    "source": {                             //API name
    "handler": "render",                     //Processes the widget function name returned from an API.
    "description" : "doughnut chart API",          //API description
    "fields" : {                             //Fields required by an API. Multiple fields are supported.
     "x" : {                                 //Field name
       "description" : "category",                 //Field description
       "type" : "string",                     //Field type
       "optional": true                       //Optional field
     },
     "y" : {
       "description" : "value",
       "type" : "int"
     }
    }
    },
    "source2":{
          ...                                     //API 2
    }
    }
    ```

-   api\_data field

    This field defines the API data. Multiple APIs are supported. The API name must be the same as that in apis. The recommended data size is within 6 KB. For more information, see the notes in the preceding example.

    ```
    "api_data":{                          //API data. Multiple APIs are supported.
      "source" : [                       //API name, which must the same as that in the apis field. The recommended data size is within 6 KB.
        {"x": "cargo", "y" : 5},
        {"x": "cargo", "y" : 22},
        {"x": "light goods", "y" : 22},
        {"x": "device", "y" : 14},
        {"x": "mineral", "y" : 15},
        {"x": "metal", "y" : 15},
        {"x": "building material", "y" : 12},
        {"x": "food", "y" : 12},
        {"x": "grain", "y" : 28}
      ],
    },
    ```


## events specifications {#section_gzl_dxl_q2b .section}

The widget interactions in DataV are implemented through the emit and events description. The emit is triggered according the events description \(event description in package.json\).

-   events description

    The events field, similar to config, is contained in the datav field. The events field defines the interaction event name, event description, and the variable name. For more information, see the notes in the preceding example.

    ```
    package.json
    {
    "events": {                 
        "click-me": {                //custom event name
            "description": "click to trigger an event",             //Event description field
            "fields": {            //Multiple variables and corresponding description can be defined.
                "value": {         //Field name, which can be customized as needed
                    "description": "callback value" 
                }
            }
        }
    }
    }
    ```

-   emit triggering

    The emit is a basic function that can throw the event name and required data of a widget as parameters. In this way, other widgets can obtain the parameter values according to the variable names. For more information, see the notes in the preceding example.

    ```
    index.js
    render: function () {
        this.container.on('click', () => {
            this.emit('click-me', data)            // The value of data must be an object and cannot be a value. The property name is the variable name.
        })
    }
    ```


## type field {#section_nsx_3xl_q2b .section}

The type field defines the widget type. For more information, see the notes in the preceding example.

```
type: ["regular_bar", ...]  //A widget can belong to different groups. Multiple widget types are separated using underscores (_), for example, "type1_type2".
    { // Common widget type
      regular: "basic chart",
      map: "map", 
      figure: 'indicator', 
      network: "networks", 
      text: "text", 
      decorate: "supporting graphics"
    }
```

