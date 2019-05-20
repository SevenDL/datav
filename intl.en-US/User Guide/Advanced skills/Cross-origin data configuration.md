# Cross-origin data configuration {#concept_k5l_ckz_q2b .concept}

## Background {#section_fs1_2kz_q2b .section}

If user A creates a visualization project in DataV, and selects API from the Data Source Type drop-down list \(shown in the following figure\), depending on where the API is hosted, the following situations may occur.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16582/15583433548623_en-US.png)

-   If the API is on a remote server and has access to a public network, select **Initiate a request from a server \(HTTP proxy\)**. The DataV backend server initiates a request to the API at the same time. The request has a 10-second timeout and cannot be changed.
-   If the API is on a local server, deselect **Initiate a request from a server \(HTTP proxy\)**, and the interface needs to be configured across origins. The API is accessed by a local browser and the timeout duration is also determined by the local browser.

## What is an issue related to cross-origin data configuration {#section_umm_hkz_q2b .section}

Assume that user A’s website needs to include data from their own website and from user B’s website.  Data on user A’s website can be accessed by the website interface <http://userA.com/page1\>. The website interface for user B is <http://userB.com/page2\>. If user A uses a Javascript AJAX request to gain access to user B’s website, user A cannot retrieve data from  userB.com.

If, for example, a Chrome browser is opened during the preceding request, the following is displayed:

```
XMLHttpRequest cannot load http://userB.com/page2. Because no ‘Access-Control-Allow-Origin’ header is present on the requested resource.Origin ‘http://userA.com/‘ is not allowed access.
```

This means we encountered a cross-domain issue. 

Reason

Because each website contains various interfaces, such as user interface, order interface and article interface, each user can put the data returned from those interfaces on their own website. This means the browsers have a **same-origin policy**, which restricts a script from one origin to obtain resources from another origin.

**Note:** **Same origin**: If two pages have the same protocol \(HTTP\), port \(80\) and host \(userA.com\), these two pages are considered to be from the same origin.

## Solution {#section_whl_mkz_q2b .section}

-   **Cross-origin between A.x.com and B.x.com**

    If the sub-origins for two sites are different,  such as http://xyz.userA.com/ and http://123.userA.com/, the cross-origin issue still exists.

    To solve this issue, you must declare the page to a higher-level origin.

    ```
    <script>
      document.domain = "x.com";
    </script>
    ```

-   **JSONP**

    Although JSONP is a commonly applied solution, it is vulnerable to Cross-Site Scripting \(XSS\) attacks. Therefore, DataV does not support this method.  

-   **Cross-Origin Resource Sharing \(CORS\)**

    **Note:** Cross-Origin Resource Sharing \(CORS\) was introduced to solve issues related to the sharing of restricted resources. Most new browsers are compatible with CORS.

    **Concept**

    Add the custom header information HTTP to user B’s website \(local API\) so that its resources can be accessed by other websites.

    **Example**

    -   Header information returned from a data server includes the following basic content:

        ```
        Access-Control-Allow-Origin: http://www.example.com
        ```

    -   If user B’s website interface data are used by many specified websites, the header information must be generated dynamically. The following example uses PHP:

        ```
        <? php 
        if (is_my_bastard($_SERVER['HTTP_ORIGIN'])) {
        header("Access-Control-Allow-Origin: {$_SERVER['HTTP_ORIGIN']}");
        }
        ? >
        ```

    -   If user B’s website interface data are used by all the other websites, use “\*”.

        ```
        Access-Control-Allow-Origin: *
        ```

    **Cookie**

    By default, CORS does not contain cookie information. If you want to add cookies, follow these steps:

    1.  Add the **withCredentials** parameter,  such as jquery:

        ```
        $.ajax({
         url: "http://userB.com/isdad",
         xhrFields: {
           withCredentials: true
         }
        });
        ```

    2.  Configure the server to allow headers with credentials and disallow the wildcard character “\*”, as follows:

        ```
        <? php 
        if (is_my_bastard($_SERVER['HTTP_ORIGIN'])) {
        header("Access-Control-Allow-Origin: {$_SERVER['HTTP_ORIGIN']}"); // Disallow “*”
        header("Access-Control-Allow-Credentials:true");
        }
        ? >
        ```

        For more information, see HTTP access control \(CORS\).


