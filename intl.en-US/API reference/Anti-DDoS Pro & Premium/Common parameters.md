# Common parameters

This topic describes the request and response parameters that each operation uses.

## Common request parameters

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|RegionId|String|Yes|The region ID of the instance. Valid values: -   cn-hangzhou: mainland China, which indicates an Anti-DDoS Pro instance
-   ap-southeast-1: outside mainland China, which indicates an Anti-DDoS Premium instance |
|Format|String|No|The format in which to return the response. Valid values: -   JSON \(default value\)
-   XML |
|Version|String|Yes|The version number of the API, in the format of YYYY-MM-DD. Set the value to 2020-01-01. |
|AccessKeyId|String|Yes|The AccessKey ID provided to you by Alibaba Cloud.|
|Signature|String|Yes|The signature string of the current request.|
|SignatureMethod|String|Yes|The encryption method of the signature string. Set the value to HMAC-SHA1. |
|Timestamp|String|Yes|The timestamp of the request. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. For example, 20:00:00 on January 1, 2020 \(UTC+8\) is written as 2020-01-01T20:00:00Z. |
|SignatureVersion|String|Yes|The version of the signature encryption algorithm. Set the value to 1.0. |
|SignatureNonce|String|Yes|A unique, random number used to prevent replay attacks. You must use different numbers for different requests. |
|ResourceOwnerAccount|String|No|The owner account \(the logon username\) of the resource that you want to access by using this API request.|

Sample requests

```
http://ddoscoo.cn-hangzhou.aliyuncs.com/?Action=DescribeInstanceIds
&RegionId=cn-hangzhou
&TimeStamp=2020-01-01T20%3A00%3A00Z
&Format=xml
&AccessKeyId=testid
&SignatureMethod=Hmac-SHA1
&SignatureNonce=NwDAxvLU6tFE0DVb
&Version=2020-01-01
&SignatureVersion=1.0
&Signature=Signature
```

## Common response parameters

API responses use the HTTP response format. Responses can be returned in either the JSON or XML format. You can specify the response format in the request. The default response format is JSON. Every response returns a unique RequestID regardless of whether the call is successful.

-   A `2xx` status code indicates a successful call.
-   A `4xx` or `5xx` status code indicates a failed call.

Sample responses

-   XML format

    ```
    <? xml version="1.0" encoding="utf-8"? > 
        <!--Result Root Node-->
        <Interface Name+Response>
            <!--Return Request Tag-->
            <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
            <!--Return Result Data-->
        </Interface Name+Response>
    ```

-   JSON format

    ```
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
        /*Return Result Data*/
        }
    ```


