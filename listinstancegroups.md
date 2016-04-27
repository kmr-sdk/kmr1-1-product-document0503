## ListInstanceGroups


* **功能描述**

　　提供了集群中每个实例组的详细信息。
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考[公共参数](gong_gong_can_shu.md)
  
　　**ClusterId**
  
　　　　需要列出实例组信息的集群标识。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**Marker**
    
　　　　分页标识。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
* **返回参数**

　　返回结果包含以下字段：
  
　　**InstanceGroups**
  
　　　　基于给定过滤条件返回指定集群的实例组列表<br>
　　　　类型：InstanceGroup 列表  (5.8 [InstanceGroup](InstanceGroup.md)) 

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
POST / HTTP/1.1
Content-Type: application/json
X-Action: ListInstanceGroups
X-Version: 2016-05-20

{
    "ClusterId": "e1b637b5-210d-45b3-bc16-0338b3c8cf8e"
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
  Content-Type:application/json
Content-Length: 462
Date: Thu, 07 Jan 2016 02:57:57 GMT
{
  "Marker": null,
  "InstanceGroups": [
    {
      "Status": {
        "State": " RUNNING "
      },
      "InstanceCount": 2,
      "Name": "gn-e51f56af-CORE",
      "InstanceGroupType": "CORE",
      "InstanceType": "kmr.compute",
      "Id": "e1b637b5-210d-45b3-bc16-0338b3c8cf8e-gn-e51f56af-CORE"
    },
    {
      "Status": {
        "State": " RUNNING "
      },
      "InstanceCount": 1,
      "Name": "gn-e51f56af-MASTER",
      "InstanceGroupType": "MASTER",
      "InstanceType": "kmr.compute",
      "Id": "e1b637b5-210d-45b3-bc16-0338b3c8cf8e-gn-e51f56af-MASTER"
    }
  ]
}
```


