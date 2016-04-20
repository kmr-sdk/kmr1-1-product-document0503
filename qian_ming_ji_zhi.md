## 签名机制


发送给KMR服务的HTTP请求中，必须包含授权参数和其他公共参数。KMR服务使用用户的Access Key ID和Secret Access Key进行加密方式来验证请求者的身份。Access Key ID和Secret Access Key由金山云发给用户，Access Key ID作为用户的身份标识，Secret Access Key作为用户和服务器端进行签名计算的密钥。

Http请求header中 Authorization字段是服务的授权参数，其格式为：

```
Authorization="[HashMethod][空格]Credential=[access_key]/[scope],SignedHeaders=[signed_headers],Signature=[signature]"
```
其中：
[HashMethod] ="KSC4-HMAC-SHA256"
[access_key] =用户Access key ID
[scope] = [timestamp]/[region]/[service][req_type]
timestamp为yyyyMMdd格式的时间戳，region为请求服务所在区域名，service为访问的服务名，req_type为请求的类型。
[signed_headers]：将Headers按照name升序排列
[signed_headers] = [header_name_1];[header_name_2]....

签名算法：

```
[signature]= sha256(sha256(sha256(sha256(sha256("KSC4"+sign_key,timestamp),region),service),req_type),string_to_sign)
```

其中：
[sign_key] =用户Secret Access Key
[stringToSign] = "KSC4-HMAC-SHA256" + "\n"
		  + [X-Ksc-Date] + "\n"
        +[scope] + “\n”
		 + SHA-256([canonical_request])
[canonical_request] = [HTTPRequestMethod] + "\n"
 		 + [CanonicalURI] + "\n"
		 + [CanonicalQueryString] + "\n"
		 + [CanonicalHeaders] + "\n"
		 + [signed_headers] + "\n"
		 + SHA-256([request_body])
[HTTPRequestMethod] = POST或GET
[CanonicalURI] = 请求URL中除去Endpoint之外的剩余部分。目前URL等于Endpoint，所以CanonicalURI为空
[CanonicalQueryString] = 空
[CanonicalHeaders]：按照[signed_headers]中的排序方式进行排序
[CanonicalHeaders] =
LowerCase (HeaderName1) + ‘:’ + Trim (HeaderValue1) + "\n"
     +LowerCase (HeaderName2) + ‘:’ + Trim (HeaderValue2) + "\n"
+.......
[request_body] = Post 请求的body部分


Python版签名代码示例：