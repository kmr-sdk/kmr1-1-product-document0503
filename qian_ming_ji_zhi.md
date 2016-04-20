## 签名机制


　　发送给KMR服务的HTTP请求中，必须包含授权参数和其他公共参数。KMR服务使用用户的Access Key ID和Secret Access Key进行加密方式来验证请求者的身份。Access Key ID和Secret Access Key由金山云发给用户，Access Key ID作为用户的身份标识，Secret Access Key作为用户和服务器端进行签名计算的密钥。

　　Http请求header中 Authorization字段是服务的授权参数，其格式为：

```
Authorization="[HashMethod][空格]Credential=[access_key]/[scope],SignedHeaders=[signed_headers],Signature=[signature]"
```
　　其中：
  
　　[HashMethod] ="KSC4-HMAC-SHA256"<br>
　　[access_key] =用户Access key ID<br>
　　[scope] = [timestamp]/[region]/[service][req_type]<br>
　　timestamp为yyyyMMdd格式的时间戳，region为请求服务所在区域名，service为访问的服务名，req_type为请求的类型。<br>
　　[signed_headers]：将Headers按照name升序排列<br>
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

```
def canonical_request(self, http_request, sign_headers):
        cr = []
        cr.append(http_request.method.upper())
        cr.append(self.canonical_uri(http_request))
        cr.append(self.canonical_query_string(http_request))
        headers_to_sign = self.headers_to_sign(http_request, sign_headers)
        cr.append(self.canonical_headers(headers_to_sign) + '\n')
        cr.append(self.signed_headers(headers_to_sign))
        if self.header_name_content_sha256 in http_request.headers:
            content_hash = self._ensure_bytes(http_request.headers[self.header_name_content_sha256])
            cr.append(content_hash)
        else:
            cr.append(self.payload(http_request))
        return '\n'.join(cr)

    def string_to_sign(self, http_request, canonical_request, scope):
        sts = [self.hash_method]
        sts.append(http_request.headers[self.header_name_date])
        sts.append(scope)
        sts.append(sha256(canonical_request.encode('utf-8')).hexdigest())
        return '\n'.join(sts)

def _sign(self, key, msg, hex=False):
        key = self._ensure_bytes(key)
        if hex:
            sig = hmac.new(key, msg.encode('utf-8'), sha256).hexdigest()
        else:
            sig = hmac.new(key, msg.encode('utf-8'), sha256).digest()
        return si

def signature(self, string_to_sign, scope, secret_key):
        parts = scope.split('/')
        ts = parts[0]
        region = parts[1]
        service = parts[2]
        req_type = parts[3]
        k_date= self._sign((self.hash_keyword + secret_key).encode('utf-8'), ts)
        k_region = self._sign(k_date, region)
        k_service = self._sign(k_region, service)
        k_signing = self._sign(k_service, req_type)
        return self._sign(k_signing, string_to_sign, hex=True)
```