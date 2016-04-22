## ListInstanceGroups


* **功能描述**

　　提供了集群中每个实例组的详细信息。
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考2.2[公共参数](gong_gong_can_shu.md)
  
　　**ClusterId**
  
　　　　需要列出实例组信息的集群标识。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**Marker**
    
　　　　分页标识。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
* **返回参数**

　　返回结果不包含任何字段

* **错误信息**

　　关于所有操作使用的通用错误信息，参考2.4[通用错误信息](tong_yong_cuo_wu_xin_xi.md)

　　**InternalServerError**
  
　　　　当KMR服务出现内部错误时出现该错误信息类型<br>
　　　　HTTP状态码：500
    
　　**BadRequest**
  
　　　　当用户输入信息有误时出现该错误信息<br>
　　　　HTTP状态码：400

* **样例**

　　**请求样例**

```
POST / HTTP/1.1
Content-Type: application/json
X-Ksc-Target: ElasticMapReduce_V1.SetTerminationProtection
{
    "JobFlowIds": ["26e6d8af-18e2-49b6-b7d1-040dfb170b3b"],
    "TerminationProtected": true
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 2
{}
```


