# Publish a project {#concept_hqf_22r_p2b .concept}

## Procedure {#section_pvm_mcm_q2b .section}

1.  Log on to the [DataV console](https://partners-intl.console.aliyun.com/#/datav).
2.  Click **Projects**.
3.  Select a project and click **Publish**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15583448669205_en-US.png)

4.  Turn on the **Publish** button. Other users have access to a project through the **Sharing URL** shown in the following sharing link.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15583448668031_en-US.png)

    **Note:** If the **Publish** switch is turned on, it indicates that the project has been published, otherwise the project is not published.

5.  Before publishing a project, you can set [Sharing Configuration](#) and [History Versions](#).

## Sharing configuration {#section_czf_hcm_q2b .section}

A random sharing link is generated when the **Publish** button is turned on. This sharing link changes each time it is turned on and the previous sharing link becomes invalid immediately and cannot be restored.

The three modes of the publishing function are as follows:

-   Public sharing
-   [Password protection sharing](#)
-   [Token protection sharing](#)

Select a mode that fits your needs to help internal and external users have access to visualization projects.

## Password protection sharing \(for Enterprise Edition\) {#section_qsb_gdm_q2b .section}

1.  In the publish window, click Password Protection and turn on the button.
2.  Enter a password. The password must contain at least 6 characters and satisfy the following three conditions:

    -   Uppercase letters A to Z
    -   Lowercase letters a to z
    -   Arabic numerals 0 to 9
    If a password is successfully set, **The password has been set** will be displayed,  otherwise the color of the password input box becomes red.

3.  Choose whether to enable the **Password/Token Expiration: 32 Hours** button.
    -   When this verification mode is enabled, after a visitor enters a password and successfully accesses a large screen, the visitor can access the large screen again within 32 hours without the password.  The visitor needs to re-enter the password after 32 hours.
    -   When this verification mode is disabled, the visitor needs to re-enter the password after one minute.

When the visitor attempts to access the URL again, the system requests the password.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15583448668033_en-US.png)

## Token protection sharing \(for Enterprise Edition\) {#section_jsk_wdm_q2b .section}

If you want to integrate a project with your permission system, you can choose this mode.

1.  Log on to the [DataV console](https://partners-intl.console.aliyun.com/#/datav).
2.  Click **Projects**.
3.  Select a project and click **Publish**.
4.  Click Token Protection in the publish window and turn on the button.
5.  Choose whether to enable the **Password/Token Expiration: 32 Hours** button.
    -   When this verification mode is enabled, after a visitor successfully accesses a large screen through a token verification, the visitor can access the large screen within 32 hours without a token verification. The visitor needs to perform the token verification again after 32 hours.
    -   When this verification mode is disabled, the visitor needs to perform the token verification again after 1 minute.

When you enable **Token Protection**, DataV generates a token for you. You need to keep it for future use.

When a visitor directly visits the page by using the page URL, the visitor receives an **Access Denied** message,  which means the access has been rejected.

To enable visitors to open this page, follow these steps:

**Note:** To prevent replay attacks, make sure that your server time is UTC +8. DataV only provides one minute error, and if the time error exceeds one minute the validation fails.

1.  Publish a project and record the code of the project. This is the last part of the URL.
2.  Connect the code and the current time, accurate to a millisecond \(ms\) with a vertical bar \(|\).
3.  Use the token to encrypt the preceding string through HMAC-SHA256 base64.
4.  Name the time and the encrypted signature as \_datav\_time and \_datav\_signature respectively.
5.  Insert the time and the encrypted signature in the `querystring` of the url one by one.

The example is as follows:

PHP:

```
<? php
  $token = "kBwoX9rFX9v4zbOT0Gjd_wr65DZ3P_WW";
  $screenID = "03d1b68faeb09671046d1ef43f588c33";
  $time = time()*1000;
  $stringToSign = $screenID.' |'.$time;
  $signature = urlencode(base64_encode(hash_hmac('sha256', $stringToSign, $token, true)));
  $url = "http://local.datav.aliyun.com:9999/share/".$screenID."?_datav_time=".$time."&_datav_signature=".$signature;
? >
<iframe width=100% height=100% src="<? =$url? >"/>
```

NODE.JS：

```
const crypto = require('crypto');
var token = "Ev97wOUSAtJusc3Vsd9O2ngr_vfVFH67";
var screenID ="14c5448c00ecde02b065c231d1659f38";
var time = Date.now();
var stringToSign = screenID +'|'+ time;
var signature = crypto.createHmac('sha256', token).update(str).digest().toString('base64');
var url="http://datav.aliyun.com/share/"+ screenID +"? _datav_time="+time+"&_datav_signature="+ encodeURIComponent(signature);
```

Java:

```
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
        String url = "http://datav.aliyun.com/share/"+ screenID +"? _datav_time="+time+"&_datav_signature="+ signature;
        return url;
    }
    /**
     * Sha405 encryption with Java Native Summary
     * @ Param STR encrypted message
     * @return
     */
    public static String HMACSHA256(byte[] data, byte[] key)
    {
        try {
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

## History versions \(unavailable for Basic Edition\) {#section_kzk_mgm_q2b .section}

A snapshot of the project content is taken when creating a version. Any edits to the archived project content cannot be synchronized to history snapshots, but can be used as a backup for previewing stable versions. 

When the history snapshot feature is enabled for the first time, it is defaulted to **Current Version** as shown in the following figure. Refresh the shared link to see the current version.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15583448668034_en-US.png)

**Note:** The history versions can be switched with each other. The rollback feature is not supported.

1.  Click **Create Version**. The current project configurations are saved as a snapshot.
    -   Enter a note in the **Note** column.
    -   The snapshot data is still retained when the **Publish** feature is disabled.
2.  To add new snapshots click **Create Version** again. Currently only three valid snapshots can be saved.
3.  To delete extra snapshots click **Delete**.
4.  To switch among snapshots and the real-time version , select a radio button in the **Status** column, as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16553/15583448668035_en-US.png)

5.  To view the project content of the selected snapshot version, refresh the sharing page.

