# Add an OSS data source {#concept_bgl_qcv_vfb .concept}

Alibaba Cloud [Object Storage Service \(OSS\)](../../../../reseller.en-US/Product Introduction/What is OSS?.md#) allows you to save and use unstructured data \(text, image, audio, and video files\) through the network at any time.

## Procedure {#section_lnc_fgq_p2b .section}

1.  Choose **Data Sources** \> **Add Source**.
2.  From the **Type** drop-down menu, select **OSS**.
3.  Enter the OSS data source information, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64454/155834846332329_en-US.png)

    -   **Name**: The display name of the data source. You can customize the display name as needed.
    -   **AK ID**: The AccessKey ID of the account that can access OSS.
    -   **AK Secret**: The AccessKey Secret of the account that can access OSS.
    -   **Region**: The region to which the target OSS data source belongs. To obtain the region information, log on to the [OSS console](https://oss.console.aliyun.com/) and click the target bucket name.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/64454/155834846332341_en-US.png)

        Set **region** to **oss-cn-shanghai**. As shown in the preceding figure, the OSS bucket is in Shanghai.

    The system automatically tests connectivity after the data source information is set.

4.  After the connectivity test is successful, click **OK**.

    The data source is automatically displayed in the data source list.


## Use the OSS data source {#section_jln_qgz_5fb .section}

1.  In the DataV console, click **Projects**, select the target project, and click **Edit**.
2.  On the displayed page, select a widget. In the data pane, select **OSS** for **Data Source Type**.
3.  From the **Select Data Source** drop-down menu, select the OSS data source you have configured before.
4.  In the **File Path** area, enter the target file path. The format must meet the following requirements:
    -   The file must be in the JSON format.
    -   The file path format is as follows: oss://bucket/file. For example, if your bucket name is myBucket and your file name is test.json, you need to enter **oss://myBucket/test.json**.
5.  Click **View Data Response** to view the effect.

