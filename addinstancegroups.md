## AddInstanceGroups


* **功能描述**

　　AddInstanceGroups用于添加实例组，目前仅支持添加一个任务实例组。一个集群中最多只能有一个任务实例组。
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考2.2[公共参数](gong_gong_can_shu.md)
  
　　**ClusterId**
  
　　　　需要添加实例组信息的集群标识。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**InstanceGroups**
  
　　　　InstanceGroup配置列表<br>
　　　　类型：InstanceGroupConfig列表  ([InstanceGroupConfig](InstanceGroupConfig.md))<br>
　　　　是否必须：是
    　　
* **返回参数**

　　返回结果包含以下字段：
  
　　**InstanceGroupIds**
  
　　　　添加成功的实例组ID列表。<br>
　　　　类型：String列表
    
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
X-Action: AddInstanceGroups
X-Version: 2016-05-20
{
    "ClusterId": "e1b637b5-210d-45b3-bc16-0338b3c8cf8e",
    "InstanceGroups": [
        {
            "InstanceGroupType": "TASK",
	            "InstanceCount": 1,
	            "InstanceType": "kmr.compute"
}
    ]
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 2
{ "InstanceGroupIds": [
    "bb26aa5a-4032-4b0d-9037-82c6b715c241"
  ] 
}
```


