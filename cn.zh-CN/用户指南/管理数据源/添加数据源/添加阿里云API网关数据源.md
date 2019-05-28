# 添加阿里云API网关数据源 {#concept_zk3_1cz_5fb .concept}

[阿里云API网关](https://www.aliyun.com/product/apigateway)，即API托管服务，涵盖API发布、管理、运维、售卖的全生命周期管理。

## 操作步骤 {#section_lnc_fgq_p2b .section}

1.  登录[DataV控制台](http://datav.aliyun.com/)，选择**我的数据** \> **添加数据**。
2.  单击**类型**下拉菜单，选择数据库类型为**阿里云API网关**。
3.  填写API网关信息，如下图所示。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64229/155901477432305_zh-CN.png)

    -   **名称**：数据源的显示名称，您可以自由命名。
    -   **域名**：API网关的调用域名，您可以进入[API网关控制台](https://apigateway.console.aliyun.com/)查看。
    -   **AppKey**：API网关接口的调用AppKey，参考[获取API定义](https://help.aliyun.com/document_detail/42740.html)，获取相关接口的AppKey。
    -   **AppSecret**：API 网关接口的调用AppSecret，参考[获取API定义](https://help.aliyun.com/document_detail/42740.html)，获取相关接口的AppSecret 。
4.  信息填写完成后，单击**确定**进行保存，完成数据源的添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用API网关数据源 {#section_jln_qgz_5fb .section}

1.  在DataV控制台上，单击**我的可视化**，选择您的项目，单击**编辑**，进入大屏编辑界面。
2.  单击选择某一组件，在数据面板中，选择**数据源类型**为**阿里云API网关**。
3.  单击**选择已有数据源**下拉菜单，选择配置完成的阿里云 API 网关数据源 。
4.  在下方**请求URL**栏内填写需要请求的接口URL路径。
5.  单击**查看数据响应结果**，数据响应成功后即可看到效果。

## 使用示例 {#section_vrs_kpt_vfb .section}

1.  获取阿里云API网关接口。

    阿里云 API 网关是面向用户的产品，您可以通过以下两种方式获取API网关接口：

    -   将您的API托管在API网关，通过DataV调用API网关进而调用您自己的接口，接入方式请参考[阿里云API网关官方帮助文档](https://help.aliyun.com/product/29462.html)。
    -   在阿里云的[云市场](https://market.aliyun.com/)上购买相关的 API 服务，通过DataV调用相关的结果，获取 API 服务的返回结果，比如 IP 定位等服务。
2.  在DataV中配置API数据源，并将结果展示在大屏上。

    本文以云市场的API服务为例子，配置方法如下：

    1.  购买云市场API服务。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64229/155901477432312_zh-CN.png)

        购买完成后进入**API网关控制台**页面，可以看到该接口的**AppKey**、**AppSecret**信息，将这些信息填写到DataV的数据源处。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64229/155901477432313_zh-CN.png)

    2.  获取API服务的域名、路径、参数，在API说明页面查询API定义，以其中的**IP定位**接口为例，可以查看到这个接口的相关信息，如下图所示。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64229/155901477432314_zh-CN.png)

        -   **域名**：iploc.market.alicloudapi.com
        -   **请求 URL**：/v3/ip
        -   **请求参数**：ip
    3.  配置数据源 。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64229/155901477432315_zh-CN.png)

    4.  填写查询参数。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64229/155901477432316_zh-CN.png)

    5.  查看查询结果。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64229/155901477432317_zh-CN.png)

    6.  使用回调参数。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64229/155901477432318_zh-CN.png)


