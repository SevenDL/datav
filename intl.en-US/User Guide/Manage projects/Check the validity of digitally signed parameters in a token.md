# Check the validity of digitally signed parameters in a token {#concept_354588 .concept}

This topic describes how to check the validity of digitally signed parameters in the token for a DataV project.

To do so, log on to the DataV console and navigate to the Publish page to enable token authentication when you publish a project. This validity check helps to authenticate the digitally signed parameters that are passed in your project URL. In addition, it protects these parameters against unauthorized changes, improving the overall security of your profile and project data.

## Background information {#section_rjq_l2u_xot .section}

Assume that your employee ID is **123** and you publish a DataV project to your system. The system calculates the project URL by using a token. After you pass your employee ID workid to the system by using the GET method as follows, the system presents your project data: `https://datav.aliyun.com/share/xxx?_datav_time=1556022195845&_datav_signature=%2BDZFj3QDIla%2F00fBZLdJMgk2Z1Ocs9MLL1GiHdYkwa0%3D&workid=123`.

However, you can change the value of the workid parameter in the project URL as the one that follows to view the profile and project data of the user with the employee ID **124**: `https://datav.aliyun.com/share/xxx?_datav_time=1556022195845&_datav_signature=%2BDZFj3QDIla%2F00fBZLdJMgk2Z1Ocs9MLL1GiHdYkwa0%3D&workid=124`.

Therefore, the system must be able to digitally sign such parameters and check the validity of these parameters so to protect against unauthorized changes when they are passed in the URL. If a user changes the value of a digitally signed parameter without authorization, the requested URL becomes inaccessible as a result.

## Prerequisites {#section_6oe_yp8_3ii .section}

-   Your project is published with token authentication enabled. For more information, see [Configure token authentication](intl.en-US/User Guide/Manage projects/Publish a project.md#).
-   The GET method is used to pass the parameters that must be protected against unauthorized changes, with these parameters added to the end of your project URL.

## Digitally sign a parameter {#section_4no_zvu_wcq .section}

The name of a digitally signed parameter starts with a `datav_sign_` string. This string can be followed by any valid characters that comprise the parameter name. As such, the regular expression for the name of a digitally signed parameter is `/^datav_sign_.*/`.

If a parameter does not comply with the preceding rule, it will not be digitally signed. Furthermore, the system does not check its validity and its value can be changed.

## Calculate a URL with digitally signed parameters {#section_sma_f4e_4vb .section}

You can run the following Node.js code to calculate a URL with digitally signed parameters:

``` {#codeblock_fkd_kuz_zy9}
const crypto = require('crypto');
const querystring = require('querystring');
const signedQueryParamReg = /^datav_sign_.*/;  // A parameter that complies with the regular expression needs to be digitally signed.

const token = "93TWnmeBtxxxxxxxxxx3thGyAgzennsS";
const screenID ="b92xxxxxxxxxxxxxxxxxx27b4c538cd4";
const time = Date.now();

const customeParams = {
  datav_sign_no: 123998,
  name: 123
};
let signParamsStr = Object.keys(customeParams)
  .filter(paramName => customeParams[paramName] && signedQueryParamReg.test(paramName))
  .sort()
  .map(param => `${param}=${customeParams[param]}`)
  .join('&');
let stringToSign = [screenID, time];
signParamsStr && stringToSign.push(signParamsStr);
stringToSign = stringToSign.join('|');
let signature = crypto.createHmac('sha256', token).update(stringToSign).digest().toString('base64');
let queryParams = {
  _datav_time: time,
  _datav_signature: signature
};

Object.keys(customeParams).forEach(paramName => {
  queryParams[paramName] = customeParams[paramName];
});

let url = `http://datav.aliyun.com/share/${screenID}?${querystring.stringify(queryParams)}`;
console.log(url);
```

The URL you obtain is as follows:

 `http://datav.aliyun.com/share/b92db8e09358c82efca0727b4c538cd4?_datav_time=1556023246894&_datav_signature=GGSbvxlemUeBoRVco8JgrJVWRcmao7NuRYt2OrGBC5g%3D&datav_sign_no=123998&name=123` 

Within the validity period of the URL:

If you change the value of the datav\_sign\_no parameter, the URL becomes inaccessible. This is because this parameter complies with the parameter-signing rule and is digitally signed. Therefore, changing the value of this parameter affects the URL calculation.

If you change the value of the name parameter, the URL remains accessible. This is because this parameter does not comply with the parameter-signing rule and is not digitally signed. Therefore, changing the value of this parameter does not affect the URL calculation.

For information about the parameter-signing rule, see [Digitally sign a parameter](#section_4no_zvu_wcq).

## Perform the validity check {#section_l7a_nyj_cmq .section}

1.  Determine which parameters must be digitally signed. That is, which parameters cannot be changed without authorization.
2.  Publish a DataV project when you enable token authentication. For more information, see [Publish a project](EN-US_TP_16553.dita#concept_hqf_22r_p2b/section_jsk_wdm_q2b).
3.  Calculate the URL of the project. For more information, see [Calculate a URL with digitally signed parameters](#section_sma_f4e_4vb).
4.  Use the URL obtained from the previous step to access the project. The system automatically checks the validity of digitally signed parameters.

    If you attempt to access the project after changing the value of a digitally signed parameter, your access request is denied.


