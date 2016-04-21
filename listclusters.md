## ListClusters

* **功能描述**

　　列出当前账户可见的所有KMR集群状态信息，允许您基于特定的条件对这些信息进行筛选；例如，基于集群创建日期和时间来筛选。每次调用默认返回100个集群，每次最多返回100个，同时会返回一个Marker来对多次ListClusters请求调用进行分页跟踪。
  
* **请求参数**
 
　　关于所有操作使用的通用参数信息，请参考2.2[公共参数](gong_gong_can_shu.md)
  
　　**ClusterStates.member.N**
  
　　　　需要列出的集群状态。<br>
　　　　类型：String列表<br>
　　　　可选值：STARTING | RUNNING | RESIZING | TRANSFERINGLOG | TERMINATED | TERMINATED_WITH_ERRORS<br>
　　　　是否必须：否
  
　　**CreatedAfter**
  
　　　　列出在某个日期和时间之后创建的集群。<br>
　　　　类型：DateTime<br>
　　　　是否必须：否
  
　　**CreatedBefore**
  
　　　　列出在某个日期和时间之前创建的集群。<br>
　　　　类型：DateTime<br>
　　　　是否必须：否
  
　　**Marker**
  
　　　　分页标识。<br>
　　　　类型：String<br>
　　　　是否必须：否
  
* **返回参数**

　　返回结果包含以下字段：
  
　　Clusters
  
　　　　当前账户满足请求中给出的过滤条件的集群列表
　　　　类型：ClusterSummary列表 (5.7 ClusterSummary)
    
　　Marker
  
　　　　用于获取下一页结果集的分页标识
　　　　类型：String
    
* **错误信息**

　　关于所有操作使用的通用错误信息，参考2.4通用错误信息
  
　　InternalServerError
  
　　　　当KMR服务出现内部错误时出现该错误信息类型
　　　　HTTP状态码：500
   
　　BadRequest
  
　　　　当用户输入信息有误时出现该错误信息
　　　　HTTP状态码：400

* **样例**

　　请求样例
  
```
POST / HTTP/1.1
Content-Type: application/json
X-Ksc-Target: ElasticMapReduce_V1.ListClusters
{
   "ClusterStates": ["RUNNING", "TERMINATED"]
   "CreatedAfter": "2016-01-08T19:00:00"
}
```

　　返回样例
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: xxx
{
    "Marker": "offset=15 & limit=5",
    "Clusters": [
        {
            "Status": {
                "State": "RUNNING"
            },
            "NormalizedInstanceMins": 14,
            "Id": "0b875523-9e95-454a-8fff-f9e592303d95",
            "Name": "test-cluster-ops-03"
        },
        {
            "Status": {
                "State": "RUNNING"
            },
            "NormalizedInstanceMins": 15,
            "Id": "26e6d8af-18e2-49b6-b7d1-040dfb170b3b",
            "Name": "test-cluster-ops-01"
        }
    ]
}
```