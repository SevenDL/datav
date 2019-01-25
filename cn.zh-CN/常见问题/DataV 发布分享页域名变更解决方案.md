# DataV 发布分享页域名变更解决方案 {#concept_rr4_btm_4gb .concept}

**为了更好地支持分享，DataV 大屏分享页域名即将从**datav.aliyun.com/share/example** 切换为 **datav.aliyuncs.com/share/example** ，本文提供了此变更可能对您的 DataV 大屏项目造成的影响及解决方案。旧域名（datav.aliyun.com）计划在3月下线。**

**说明：** DataV 大屏分享页域名变更可能会对您的大屏项目产生影响，对您造成的不便敬请谅解。请按照本文档提供的方法及时进行排查并解决问题。在此期间，新域名和旧域名会共存一段时间，方便您进行过渡。旧域名（datav.aliyun.com）计划在3月下线。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/120367/154840990438181_zh-CN.png)

## 域名变更的影响 {#section_a4x_wrk_q2b .section}

-   使用了 `API` 作为数据源的组件，可能会因为域名变更导致跨域请求被拦截。
-   **轮播页面**组件或者 **iframe**组件内打开的页面，可能会因为[跨域](../../../../../cn.zh-CN/用户指南/进阶技巧/跨域数据配置.md#)限制导致 iframe 页面无法在新域名**datav.aliyuncs.com** 下被访问。
-   使用了 **DataV数据代理服务** 数据源的组件，可能会因为域名变更导致[跨域](../../../../../cn.zh-CN/用户指南/进阶技巧/跨域数据配置.md#)请求被拦截。

## **域名变更问题的解决方案** {#section_byf_2fd_bfb .section}

DataV 在发布页面提供了新的**分享链接**，您可以打开新的分享链接测试大屏是否正常运行。如果无法正常运行，您可以按照以下方式进行排查并解决问题。

1.  检查您大屏中的组件是否使用了`API` 作为数据源，如果是，请执行以下步骤：
    1.  如果组件的数据配置中没有勾选**需要 cookie \(不选择代理并且需要获取 cookie 时使用\)**，请确保请求响应头 response headers 里包含： `Access-Control-Allow-Origin: *` 。
    2.  如果组件的数据配置中勾选了**需要 cookie \(不选择代理并且需要获取 cookie 时使用\)**，需要根据 `request.headers.referer` 动态返回可以被跨域请求的响应头 response headers，示例如下：

        |当前页面地址|request.headers.referer|满足要求的响应头 response headers|
        |:-----|:----------------------|:------------------------|
        |编辑页（http）：http://datav.aliyun.com/admin/screen/216787|http://datav.aliyun.com/admin/screen/216787|         ```
Access-Control-Allow-Origin: http://datav.aliyun.com
        ```

 |
        |编辑页（https）：https://datav.aliyun.com/admin/screen/216787|https://datav.aliyun.com/admin/screen/216787|         ```
Access-Control-Allow-Origin: https://datav.aliyun.com
        ```

 |
        |旧版分享页（https）：https://datav.aliyun.com/share/xxx|https://datav.aliyun.com/share/xxx|         ```
Access-Control-Allow-Origin: https://datav.aliyun.com
        ```

 |
        |旧版分享页（http）：http://datav.aliyun.com/share/xxx|http://datav.aliyun.com/share/xxx|         ```
Access-Control-Allow-Origin: http://datav.aliyun.com
        ```

 |
        |新版分享页（https）：https://datav.aliyuncs.com/share/xxx|https://datav.aliyuncs.com/share/xxx|         ```
Access-Control-Allow-Origin: https://datav.aliyuncs.com
        ```

 |
        |新版分享页（http）：http://datav.aliyuncs.com/share/xxx|http://datav.aliyuncs.com/share/xxx|         ```
Access-Control-Allow-Origin: http://datav.aliyuncs.com
        ```

 |

2.  检查您大屏中是否使用了**iframe**或者**轮播页面**组件，如果是，请执行以下步骤：
    1.  访问新版发布页的分享链接，检查 iframe 页面内容是否正常加载，如果无法正常加载，请执行下一步。

        **说明：** iframe 页面没有正常加载，说明这个页面在响应头里做了**X-Frame-Options** 限制，您填入的 iframe 页面地址不支持在 **datav.aliyncs.com**下被访问，需要按照以下步骤增加跨域支持。

    2.  删除响应头内的`X-Frame-Options` 字段，或者修改响应头内的`X-Frame-Options` 的内容，示例如下：

        |当前页面地址|满足要求的响应头 response headers 需要包含的字段内容|
        |:-----|:----------------------------------|
        |编辑页（http）：http://datav.aliyun.com/admin/screen/216787|         ```
X-Frame-Options: ALLOW-FROM http://datav.aliyun.com
        ```

 |
        |编辑页（https）：https://datav.aliyun.com/admin/screen/216787|         ```
X-Frame-Options: ALLOW-FROM https://datav.aliyun.com
        ```

 |
        |旧版分享页（https）：https://datav.aliyun.com/share/xxx|         ```
X-Frame-Options: ALLOW-FROM https://datav.aliyun.com
        ```

 |
        |旧版分享页（http）：http://datav.aliyun.com/share/xxx|         ```
X-Frame-Options: ALLOW-FROM http://datav.aliyun.com
        ```

 |
        |新版分享页（https）：https://datav.aliyuncs.com/share/xxx|         ```
X-Frame-Options: ALLOW-FROM https://datav.aliyuncs.com
        ```

 |
        |新版分享页（http）：http://datav.aliyuncs.com/share/xxx|         ```
X-Frame-Options: ALLOW-FROM http://datav.aliyuncs.com
        ```

 |

3.  检查您大屏中的组件是否使用了**DataV 数据代理服务**数据源，如果是，请执行以下步骤：
    -   方法一：
        1.  单击[此处](https://files.alicdn.com/tpsservice/3b30abf1b9f8a2056cc135d2a6587bb9.zip)下载 DataVProxy 包中的 app.js 文件。
        2.  将下载的 app.js 文件替换服务器 DataVProxy 所在根目录下的同名文件，并重启服务器。
    -   方法二：
        1.  打开服务器中 DataVProxy 根目录下的 app.js 文件。
        2.  修改 app.js第20行的跨域头判断信息，增加 `datav.aliyuncs.com` 支持，如下所示。

            ```
            // 旧的 line 20：
            if (this.request.header.origin && this.request.header.origin.match(/(datav.aliyun.com|datav-ap-northeast-1.alibabacloud.com|datav-ap-southeast-1.alibabacloud.com)(:\d+)?/)) {
            
            // 新的 line 20：
            if (this.request.header.origin && this.request.header.origin.match(/(datav.aliyun.com|datav-ap-northeast-1.alibabacloud.com|datav-ap-southeast-1.alibabacloud.com|datav.aliyuncs.com)(:\d+)?/)) {
            
            ```

        3.  修改完成后，保存 app.js 文件并重启服务器。

