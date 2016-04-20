## 公共参数

| 名称 | 描述 | 是否必须 |
| -- | -- | -- |
| Host | KMR服务的Host name | 是 |
| Authorization | 授权参数 | 是 |
| Content-Type | 数据结构类型（application/json） | 是 |
| X-Ksc-Target | 请求的目标操作，例如：
EX-Ksc-TargetlasticMapReduce_V1.ListClusters | 是 |
| X-Ksc-Content-Sha256 | Sha256哈希值，用于计算签名 | 否 |
| X-Ksc-Date | 请求发出的时间，格式：
yyyyMMdd'T'HHmmss'Z'  | 是 |
