# Request signatures

You must sign all API requests to ensure security. Alibaba Cloud uses the request signature to verify the identity of the API caller. Each API request must contain the signature, regardless of whether it is sent by using HTTP or HTTPS.

## Overview

You must add the signature to Anti-DDoS Pro or Anti-DDoS Premium API requests in the following format:

```
https://Endpoint/?SignatureVersion=1.0&SignatureMethod=HMAC-SHA1&Signature=CT9X0VtwR86fNWSnsc6v8YGOjuE%3D&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf
```

In the URL:

-   SignatureMethod: the encryption method of the signature string. Set the value to `HMAC-SHA1`.
-   SignatureVersion: the version of the signature encryption algorithm. Set the value to `1.0`.
-   SignatureNonce: a unique random number used to prevent replay attacks. You must use different random numbers for different requests. We recommend that you use universally unique identifiers \(UUIDs\).
-   Signature: the signature generated after the request has been symmetrically encrypted by using the AccessKey secret.

The signature encryption algorithm complies with RFC 2104 HMAC-SHA1 specifications. The AccessKey secret is used to calculate the hash-based message authentication code \(HMAC\) value of the encoded and sorted query string, and the HMAC value is used as the signature string. Request signatures include operation-specific parameters. Therefore, the signature of a request varies based on the request parameters. To calculate a signature, follow the steps in this topic.

```
Signature = Base64( HMAC-SHA1( AccessKey Secret, UTF-8-Encoding-Of(
StringToSign)) )
```

## Step 1: Compose and encode a string-to-sign

1.  Create a canonicalized query string
    1.  by arranging the request parameters \(including all common and operation-specific parameters except Signature\) in alphabetical order.

        **Note:** If you use the GET method to submit the request, these parameters are the part located after the question mark \(?\) and connected by the ampersands \(&\) in the request uniform resource identifier \(URI\).

    2.  Encode the canonicalized query string in UTF-8. The following table describes the encoding rules.

        |Character|Encoding rule|
        |---------|-------------|
        |Uppercase letters, lowercase letters, digits, and some special characters such as hyphens \(-\), underscores \(\_\), periods \(.\), and tildes \(~\)|Not encoded.|
        |Other characters|These characters must be percent encoded in the `%XY` format. `XY` represents the ASCII code of the characters in hexadecimal notation. For example, double quotation marks \("\) are encoded as `%22`.|
        |Extended UTF-8 characters|These characters are encoded in the `%XY%ZA...` format.|
        |Spaces|Spaces must be encoded as `%20`. Do not encode spaces as plus signs \(+\). This encoding rule is different from the `application/x-www-form-urlencoded` MIME encoding algorithm. For example, this algorithm is used by the `java.net.URLEncoder` class provided by the Java standard library. You can encode a space based on the encoding rule for the standard library. Then, replace the plus sign \(+\) with `%20`, the asterisk \(\*\) with `%2A`, and `%7E` with a tilde \(~\) in the encoded string to obtain an encoded string that complies with the preceding encoding rules. To do this, you can use the `percentEncode` method:

        ```
private static final String ENCODING = "UTF-8";
private static String percentEncode(String value) throws UnsupportedEncodingException 
{
return value ! = null ? URLEncoder.encode(value, ENCODING).replace("+", "%20").replace("*", "%2A").replace("%7E", "~") : null;
}
        ``` |

    3.  Connect the encoded parameters and their values by using equal signs \(=\).
    4.  Sort the connected parameter and value pairs in the order specified in step 1.i and connect the pairs by using ampersands \(&\) to obtain a canonicalized query string.
2.  Create a string-to-sign from the encoded canonicalized query string.

    ```
    StringToSign=
          HTTPMethod + “&" +
          percentEncode("/") + "&" +
          percentEncode(CanonicalizedQueryString)
    ```

    In the preceding rules,

    -   HTTPMethod indicates the HTTP method used to send the request, such as GET.
    -   percentEncode\("/"\) is the encoded value \("%2F"\) of a forward slash \(/\) based on the URL encoding rules described in step 1.i.
    -   percentEncode\(CanonicalizedQueryString\) is the string constructed by using the canonicalized query string based on the URL encoding rules described in step 1.ii.

## Step 2: Calculate the signature

1.  Calculate the RFC 2104-compliant HMAC value of the string-to-sign.

    **Note:** Use the SHA1 algorithm to calculate the HMAC value of the string-to-sign. The combination of your AccessKey secret and an ampersand \(&\) \(ASCII code 38\) that follows the secret is used as the key for HMAC calculation.

2.  Encode the HMAC value in Base64 to obtain the signature string
3.  Add the signature string to the request as the Signature parameter.

    **Note:** When the obtained signature value is submitted as the final request parameter value, the value must be URL-encoded like other parameters based on rules defined in [RFC 3986](https://tools.ietf.org/html/rfc3986).


## Signature examples

Use the DescribeInstanceIds operation as an example. Assume that the AccessKey ID is `testid` and the AccessKey Secret is `testsecret`. Request URL to be signed:

```
http://ddoscoo.cn-hangzhou.aliyuncs.com/?Timestamp=2020-01-01T12%3A00%3A00Z&Format=XML&AccessKeyId=testid&Action=DescribeInstanceIds&SignatureMethod=HMAC-SHA1&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf&Version=2020-01-01&SignatureVersion=1.0
```

The signature string calculated by using `testsecret&`:

```
OLeaidS1JvxuMvnyHOwuJ+uX5qY=
```

Add the Signature parameter to the request and set the value to the calculated signature string. The URL of the signed request:

```
http://ddoscoo.cn-hangzhou.aliyuncs.com/?SignatureVersion=1.0&Action=DescribeInstanceIds&Format=XML&SignatureNonce=3ee8c1b8-83d3-44af-a94f-4e0ad82fd6cf&Version=2020-01-01&AccessKeyId=testid&Signature=OLeaidS1JvxuMvnyHOwuJ+uX5qY=&SignatureMethod=HMAC-SHA1&Timestamp=2020-01-01T12%3A00%3A00Z
```

