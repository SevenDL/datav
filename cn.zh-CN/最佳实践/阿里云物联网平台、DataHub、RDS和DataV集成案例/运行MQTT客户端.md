# 运行MQTT客户端 {#task_zms_4xh_ffb .task}

-   下载Eclipse软件，并配置好Java环境。
-   此Demo为maven工程，请先安装maven。

1.  参考[阿里云物联网平台文档](https://help.aliyun.com/document_detail/42693.html)，选择**设备端开发指南** \> **JAVA-SDK**，下载[iotx-sdk-mqtt-java](http://aliyun-iot.oss-cn-hangzhou.aliyuncs.com/iotx-sdk-java/iotx-sdk-mqtt-java-20170526.zip?spm=a2c4g.11186623.2.11.641652276CMj67&file=iotx-sdk-mqtt-java-20170526.zip)并解压。 
2.  打开Eclipse应用，选择**file** \> **import** \> **Existing Maven Projects**，导入上一步中的解压后的Java SDK文件。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21750/155410416712652_zh-CN.png)

 
3.  双击打开SimpleClient4IOT.java文件。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21750/155410416712656_zh-CN.png)

 
4.   配置设备三元组和topic。修改deviceName、productKey、secret、subTopic、pubTopic变量，如下图所示。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21750/155410416712658_zh-CN.png)

 

    **说明：** 进入阿里云物联网控制台，单击物联网平台的**设备**，选择**查看**，获取以上信息。subTopic和pubTopic与上图保持一致即可。

    ```
    private static String subTopic = "/" + productKey + "/" + deviceName + "/user/get";
    private static String pubTopic = "/" + productKey + "/" + deviceName + "/user/update";
    ```

5.   修改content，如下图所示。![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21750/155410416712662_zh-CN.png)

 

    ```
    String content1 = "{'content':'shoen1','age':'20'}";
    String content2 = "{'content':'shoen2','age':'21'}";
    String content3 = "{'content':'shoen3','age':'22'}";
    
    
    MqttMessage message1 = new MqttMessage(content1.getBytes("utf-8"));
    MqttMessage message2 = new MqttMessage(content2.getBytes("utf-8"));
    MqttMessage message3 = new MqttMessage(content3.getBytes("utf-8"));
    
    message1.setQos(0);
    message2.setQos(0);
    message3.setQos(0);
    
    //System.out.println(System.currentTimeMillis() + "消息发布:---");
    sampleClient.publish(pubTopic, message1);
    sampleClient.publish(pubTopic, message2);
    sampleClient.publish(pubTopic, message3);
    ```

6.  单击**运行**。 运行成功后，返回如下信息。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/21750/155410416712664_zh-CN.png)


