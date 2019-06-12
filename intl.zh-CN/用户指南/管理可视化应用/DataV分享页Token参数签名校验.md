# DataV分享页Token参数签名校验 {#concept_354588 .concept}

本文档为您介绍在发布DataV大屏时，使用**Token参数签名校验**的方法。通过Token参数签名校验功能，您可以对大屏交互时传递的参数进行签名鉴权，保证大屏的URL访问链接的参数不能被篡改，从而提高大屏数据以及用户信息的安全性。

## 前提条件 {#section_6oe_yp8_3ii .section}

在使用**Token参数签名校验**前，请确保：

-   大屏使用[Token验证（企业版功能）](intl.zh-CN/用户指南/管理可视化应用/发布可视化应用.md#section_jsk_wdm_q2b)的方式进行发布。
-   大屏以Get的方式在URL中传递参数（直接在URL后面加参数）。
-   大屏URL中传递的参数要求不能被篡改。

## 背景信息 {#section_d7i_lkc_bms .section}

下文以一个示例说明**Token参数签名校验**的使用背景。

某用户的系统嵌入了DataV大屏，URL通过Token计算，通过Get方式传递用户的工号给大屏展示相对应的数据，可以使用`https://datav.aliyun.com/share/xxx?_datav_time=1556022195845&_datav_signature=%2BDZFj3QDIla%2F00fBZLdJMgk2Z1Ocs9MLL1GiHdYkwa0%3D&workid=123`来访问大屏。

其中workid（工号）为大屏传递的参数，存在被篡改的可能。比如工号为123的员工将URL改成`https://datav.aliyun.com/share/xxx?_datav_time=1556022195845&_datav_signature=%2BDZFj3QDIla%2F00fBZLdJMgk2Z1Ocs9MLL1GiHdYkwa0%3D&workid=124`，就可以看到工号为124的员工的资料。因此需要对用户传递的参数进行签名鉴权，保证计算得到的URL的参数不能被更改，如果私自更改了传参，页面将无法访问。

## 签名参数规则 {#section_4no_zvu_wcq .section}

需要加入签名的参数，其参数名需以`datav_sign_`开头，后面可以带任何有效的参数名字符。由此可得此参数名的正则表达式为`/^datav_sign_.*/`。

不符合签名参数规则的参数，将不会进行参数签名校验，允许修改参数值。

## 带签名参数的URL计算 {#section_sma_f4e_4vb .section}

Node.js代码示例如下。

``` {#codeblock_fkd_kuz_zy9}
const crypto = require('crypto');
const querystring = require('querystring');
const signedQueryParamReg = /^datav_sign_.*/;  // 符合此正则表达式的参数是需要签名的。

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

使用以上代码示例得到的URL为：`http://datav.aliyun.com/share/b92db8e09358c82efca0727b4c538cd4?_datav_time=1556023246894&_datav_signature=GGSbvxlemUeBoRVco8JgrJVWRcmao7NuRYt2OrGBC5g%3D&datav_sign_no=123998&name=123`，在URL的有效期内，如果修改了datav\_sign\_no字段的值，链接将无法访问；如果修改了name字段的值，链接仍然可以访问，因为datav\_sign\_no符合[签名参数规则](#section_4no_zvu_wcq)，参与了签名计算，而name不符合签名参数规则，不会进行签名计算。

## 使用流程 {#section_l7a_nyj_cmq .section}

1.  确定需要签名计算的参数名（即不允许被篡改的参数）。
2.  在大屏开发完成后，使用[Token验证](ZH-CN_TP_16553_V6.dita#concept_hqf_22r_p2b/section_jsk_wdm_q2b)的方式发布大屏。
3.  参考[带签名参数的URL计算](#section_sma_f4e_4vb)，计算大屏的URL。
4.  使用上一步中计算得到的URL访问大屏，在大屏访问过程中，系统会自动进行参数签名校验。

    如果参数签名校验功能正常，当您修改了签名参数，再次访问此URL时，访问会被拒绝。


