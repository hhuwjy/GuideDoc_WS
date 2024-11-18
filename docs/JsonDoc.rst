**MQTT_set 配置文件说明**
############################################################################################################


    PLCnext Engineer工程中采集到的数据通过MQTT APP上送至平台，只需简单修改MQTT_set配置文件，即可完成上送。


一、Json字段说明
===========================================================================================================


    **"ConnectSetting"为MQTT连接设置，其中各字段的含义为：**

        "ClientId"：客户端ID（可任意取名）
  
        "IpAdress"：云平台的IP地址

        "Port"：云平台的端口号

        "UserName”：用户名

        "UserPasswd"：密码

        “UseTls”：是否使用mqtts（**默认为true**）


    **"IecData"为上送数据配置，其中各字段的含义为：**

        "SendTopic"：topic主题

        "GrpcVarName"：PLCnext Engineer中变量名（需建立外部变量，"Arp.Plc.Eclr/"前缀保持不变，变量名写在后面，如 "Arp.Plc.Eclr/test"）


    **"FlagVariable"为心跳配置，其中各字段的含义为:**

        "xMqttConnectStatus"：PLCnext与云平台的连接状态（**默认字段，不可修改**）


二、注意事项
===========================================================================================================

    1) IecData为数组字段，若有多个需要上送的变量，则按照示例格式复制数组内容即可，示例如下：

    .. image:: ../source/images/Json.png
       


    2) 用户修改完Json配置后，建议检查一下json格式，格式不正确会导致MQTT APP报错
    
    推荐：`Json文档格式在线检查 <https://www.bejson.com/explore/index_new/#google_vignette>`_



    3) 更新完Json文件后，可利用TransferFile小工具将更新后的Json文件传输至PLCnext控制器中

   

    


