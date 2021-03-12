# Common parameters

Common request parameters must be included in all Anti-DDoS Origin API requests.

## Sample common parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|DdosRegionId|String|Yes|The region of the DDoS Origin service. Valid values:-   cn-hangzhou
-   cn-shanghai
-   cn-qingdao
-   cn-beijing
-   cn-zhangjiakou
-   cn-huhehaote
-   cn-shenzhen
-   cn-hongkong
-   us-west-1 |
|Format|String|No|The format in which to return the response. Valid values:-   JSON \(default\)
-   XML |
|Version|String|Yes|The version number of the API, in the format of YYYY-MM-DD. Set the value to 2017-11-20.|
|AccessKeyId|String|Yes|The AccessKey ID provided to you by Alibaba Cloud.|
|Signature|String|Yes|The signature string of the current request.|
|SignatureMethod|String|Yes|The encryption method of the signature string. Set the value to HMAC-SHA1.|
|Timestamp|String|Yes|The timestamp of the request. Specify the time in the ISO 8601 standard in the YYYY-MM-DDThh:mm:ssZ format. The time must be in UTC.For example, 2013-01-10T12:00:00Z indicates January 10, 2013, 20:00:00 \(UTC+8\). |
|SignatureVersion|String|Yes|The version of the signature encryption algorithm. Set the value to 1.|
|SignatureNonce|String|Yes|A unique, random number used to prevent replay attacks. You must use different numbers for different requests.|
|ResourceOwnerAccount|String|No|The name of the account that owns the resource that you want to access by using this API request.|

**Examples**

```
https://ddosbgp.aliyuncs.com/?Action=DescribeOnDemandInstance
&DdosRegionId=cn-hangzhou
&InstanceId=ddosbgp-cn-xxx
&Format=xml
&Version=2017-11-20
&Signature=xxxx%xxxx%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&TimeStamp=2012-06-01T12:00:00Z
```

## Common response parameters

API responses use the HTTP response format where a 2xx status code indicates a successful call and a 4xx or 5xx status code indicates a failed call. Response data can be returned in either the JSON or XML format. You can specify the response format in the request. The default response format is XML.

Every response returns a unique RequestId regardless of whether the call is successful.

-   XML format

    ```
    <? xml version="1.0" encoding="utf-8"? > 
        <!--Result Root Node-->    <Interface Name+Response>        <!--Return Request Tag-->        <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
            <!--Return Result Data-->    </Interface Name+Response>
    ```

-   JSON format

    ```
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
        /*Return result data*/    }           
    ```


