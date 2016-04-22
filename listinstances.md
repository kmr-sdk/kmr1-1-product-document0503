## ListInstances


* **功能描述**

　　提供了KMR集群中的实例信息，这些实例是您在创建集群时由 KMR服务帮您申请的虚拟机实例。您可以根据实例组标识、实例组角色选择您想查看的实例，每次调用可以返回最多50个实例，但可以返回一个marker来跟踪跨多个ListInstances簇列表分页调用。
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考2.2[公共参数](gong_gong_can_shu.md)
  
　　**ClusterId**
  
　　　　需要列出实例组信息的集群标识。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**InstanceGroupId**
  
　　　　需要列出实例的实例组ID，如果不提供默认值，列出所有实例组的实例<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**InstanceGroupTypes**
  
　　　　需要列出的实例的实例组角色，合法的实例组角色有: MASTER、CORE、TASK，如果不提供默认提供所有角色的实例组中的实例<br>
　　　　类型：String列表<br>
　　　　是否必须：否
    
　　**Marker**
  
　　　　分页标识。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
* **返回参数**

　　返回结果包含以下字段：
  
　　**Instances**
  
　　　　Instance结果<br>
　　　　类型：Instance列表 (5.10 Instance) 
    
　　**Marker**
  
　　　　用于获取下一页结果集的分页标识<br>
　　　　类型：String

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
GET / HTTP/1.1
POST / HTTP/1.1
Content-Type: application/json
X-Ksc-Target: ElasticMapReduce_V1.ListInstances
{
    "ClusterId": "e1b637b5-210d-45b3-bc16-0338b3c8cf8e",
    "InstanceGroupId": "",
    "InstanceGroupTypes": ["MASTER"]
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 2
{}
```


