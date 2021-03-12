# Common parameters

Common request parameters must be included in all API operations of the anti-DDoS protection package.

## Common request parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|DdosRegionId|String|Yes|The region of the protection package. Valid values: -   cn-hangzhou
-   cn-shanghai
-   cn-qingdao
-   cn-beijing
-   cn-zhangjiakou
-   cn-huhehaote
-   cn-shenzhen
-   cn-hongkong
-   us-west-1 |
|Format|String|No|The format of the response. Valid values: -   JSON \(default\)
-   XML |
|Version|String|Yes|The version number of the API, in the format of YYYY-MM-DD. Example: 2018-07-20.|
|AccessKeyId|String|Yes|The AccessKey ID provided to you by Alibaba Cloud.|
|Signature|String|Yes|The signature string of the current request.|
|SignatureMethod|String|Yes|The encryption algorithm of the signature string. Set the value to HMAC-SHA1.|
|Timestamp|String|Yes|The timestamp of the request. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. For example, 2013-01-10T12:00:00Z indicates January 10, 2013, 20:00:00 \(UTC+8\). |
|SignatureVersion|String|Yes|The version of the signature encryption algorithm. Set the value to 1.|
|SignatureNonce|String|Yes|A unique and randomly generated number used to prevent replay attacks. Users must use different numbers for different requests.|
|ResourceOwnerAccount|String|No|The name of the account that owns the resource to be accessed through this API request.|

**Examples**

```
https://ddosbgp.aliyuncs.com/?Action=DescribeInstanceList
&DdosRegionId=cn-hangzhou
&InstanceId=ddosbgp-cn-xxx
&Format=xml
&Version=2018-07-20
&Signature=xxxx%xxxx%3D
&SignatureMethod=HMAC-SHA1
&SignatureNonce=15215528852396
&SignatureVersion=1.0
&AccessKeyId=key-test
&TimeStamp=2012-06-01T12:00:00Z
```

## Common response parameters

API responses use the HTTP response format where a status code of 2XX indicates a successful call and a status code of 4XX or 5XX indicates a failed call. Response data can be returned in either the JSON or XML format. You can specify the response format when you are making the request. The default response format is XML.

Every response has a unique RequestId regardless of whether the call was successful or not.

-   XML format

    ```
    <? xml version="1.0" encoding="utf-8"? > 
        <!--Result root node-->
        <Operation name+Response>
            <!--Return request tag-->
            <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
            <!--Return result data-->
        </Operation name+Response>
    ```

-   JSON format

    ```
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
        /*Return result data*/
        }           
    ```


