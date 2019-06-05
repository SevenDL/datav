# Publish a project {#concept_hqf_22r_p2b .concept}

This topic describes how to publish a project and configure access control, the authentication methods, and the publish content for the project.

## Procedure {#section_akl_km1_t2b .section}

1.  Log on to the [DataV console](https://partners-intl.console.aliyun.com/#/datav).
2.  Click **Projects**.
3.  Select a project and click **Publish**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15597267189205_en-US.png)

4.  Turn on **Publish**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15597267198031_en-US.png)

    After you turn on **Publish**, the system automatically generates a project URL. Other users can access your project by using this URL. However, this URL takes effect only once when users first access it.


## Configure access control {#section_czf_hcm_q2b .section}

You can make a DataV project public or encrypt it with either one of the following authentication methods:

-   Password authentication.
-   Token authentication.

For more information about these two authentication methods, see the sections [Configure password authentication](#section_qsb_gdm_q2b) and [Configure token authentication](#section_jsk_wdm_q2b).

## Configure password authentication \(for Enterprise Edition\) {#section_qsb_gdm_q2b .section}

1.  In the **Authentication Method** area, select **Password**.
2.  In the **Password** field, enter a password. The password must contain at least six characters, including at least one uppercase letter, one lowercase letter, and one number.

    **Note:** If a password is set, the console displays a message **The password has been set**.

3.  \(Optional\) Set the **Expiration** date.

    **Note:** You can set the expiration date only after you set a password or turn on token authentication.

    -   If you turn on **Expiration**, you can set the validity period of the password. The maximum validity period is 32 hours. After a user enters the password and accesses the project for the first time, the user can access the project within the validity period without a password.
    -   If you turn off **Expiration**, users who want to access the project must enter the password.

A password is required when a user accesses the project after the password is set for the first time.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15597267198033_en-US.png)

## Configure token authentication \(for Enterprise Edition\) {#section_jsk_wdm_q2b .section}

You can turn on token authentication to publish a project and grant access to this project according to your permissions.

In the **Authentication Method** area, select **Token** and follow these steps:

-   \(Optional\) Set the **Expiration** date.
    -   If you turn on **Expiration**, you can set the validity period of the password. The maximum validity period is 32 hours. After a user enters the password and accesses the project for the first time, the user can access the project within the validity period without a password.
    -   If you turn off **Expiration**, users who want to access the project must enter the password.
-   Obtain the token.

    After you turn on **Token** authentication, DataV automatically generates a token. We recommend that you save this token for subsequent use.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/155972671947875_en-US.png)


When a user accesses the project by using the URL, the user receives an **Access Denied** message, indicating that the access is rejected. To allow the user to access this project by using the URL, follow these steps:

**Note:** To prevent replay attacks, make sure that your server time is UTC+8. The server time and local time can differ by one minute. If the difference exceeds one minute, the validation fails.

1.  Publish a project and save the project code \(the last segment of the project URL\).
2.  Separate the project code and the current time \(in milliseconds\) with a vertical bar \(|\).
3.  Use the token to encrypt the preceding string through HMAC-SHA256 Base64.
4.  Name the time and the encrypted signature as \_datav\_time and \_datav\_signature respectively.
5.  Insert the time and the encrypted signature in the query string of the url parameter.

    **Note:** If you use the GET method to pass parameters in your project URL, we recommend that you use the token signature validation for security. For more information, see [Authenticate parameters by using token signature validation on the DataV publish page](reseller.en-US/.md#).


Examples:

-   PHP:

    ``` {#codeblock_stw_ncc_ui2}
    <?php
      $token = "kBwoX9rFX9v4zbOT0Gjd_wr65DZ3P_WW";
      $screenID = "03d1b68faeb09671046d1ef43f588c33";
      $time = time()*1000;
      $stringToSign = $screenID.'|'.$time;
      $signature = urlencode(base64_encode(hash_hmac('sha256', $stringToSign, $token, true)));
      $url = "http://local.datav.aliyun.com:9999/share/".$screenID."?_datav_time=".$time."&_datav_signature=".$signature;
    ?>
    <iframe width=100% height=100% src="<?=$url?>"/>
    ```

-   Node.js:

    ``` {#codeblock_4hv_z0r_yn1}
    const crypto = require('crypto');
    var token = "Ev97wOUSAtJusc3Vsd9O2ngr_vfVFH67";
    var screenID ="14c5448c00ecde02b065c231d1659f38";
    var time = Date.now();
    var stringToSign = screenID +'|'+ time;
    var signature = crypto.createHmac('sha256', token).update(str).digest().toString('base64');
    var url="http://datav.aliyun.com/share/"+ screenID +"?_datav_time="+time+"&_datav_signature="+ encodeURIComponent(signature);
    ```

-   Java:

    ``` {#codeblock_mon_i05_3qh}
    package com.company;
    import java.security.*;
    import java.util.Date;
    import javax.crypto.*;
    import javax.crypto.spec.SecretKeySpec;
    import org.apache.commons.codec.binary.Base64;
    import java.net.URLEncoder;
    public class TokenTest {
        public static String getSignedUrl(String screenID, String token){
            Date date = new Date();
            Long time = date.getTime();
            String stringToSign = screenID + "|" + time;
            String signature = HMACSHA256(stringToSign.getBytes(), token.getBytes());
            String url = "http://datav.aliyun.com/share/"+ screenID +"?_datav_time="+time+"&_datav_signature="+ signature;
            return url;
        }
        /**
         *  SHA256 encryption by using the native abstraction of Java
         * @param str Encrypted packet
         * @return
         */
        public static String HMACSHA256(byte[] data, byte[] key)
        {
            try  {
                SecretKeySpec signingKey = new SecretKeySpec(key, "HmacSHA256");
                Mac mac = Mac.getInstance("HmacSHA256");
                mac.init(signingKey);
                return URLEncoder.encode(byte2Base64(mac.doFinal(data)));
            } catch (NoSuchAlgorithmException e) {
                e.printStackTrace();
            } catch (InvalidKeyException e) {
                e.printStackTrace();
            }
            return null;
        }
        private static String byte2Base64(byte[] bytes){
            return Base64.encodeBase64String(bytes);
        }
        public static void main(String[] args) throws Exception {
            System.out.println(getSignedUrl("screenId", "token"));
        }
    }
    ```


## Configure the publish content \(for Enterprise Edition\) {#section_kzk_mgm_q2b .section}

You can set the version of the project that other users can access. By default, the latest version is displayed. You can also display an existing version as needed.

-   If you click **Live Copy**, all modifications made on the canvas are synchronized to the project in real time. Users can view the modifications after you publish the latest project.
-   If you click **Snapshots**, only the snapshot of the project content is displayed. Modifications made on the canvas are not synchronized to the project, but can be used as a backup for previewing a project version. To publish a snapshot, follow these steps:
    1.  In the **Content to Publish** area, click **Snapshots**.
    2.  Click **Create Snapshot**. The current project configurations are saved as a snapshot.

        **Note:** You can enter a note for the snapshot as needed. The snapshot data is saved if **Publish** is turned off.

    3.  Click **Create Snapshot** to add an existing snapshot. Currently, you can create up to three snapshots.
    4.  Click the **Delete** icon to delete a snapshot that you no longer need.

        **Note:** Currently, you can only switch among a snapshot and the real-time version. A snapshot cannot be restored after it is deleted. Therefore, we recommend that you exercise caution when performing this action.

    5.  Click the green icon \(outlined in red in the following figure\) to switch among snapshots.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15597267198035_en-US.png)

    6.  Refresh the publish page to view the publish content.

