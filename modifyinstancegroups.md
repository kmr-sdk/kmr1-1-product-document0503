## ModifyInstanceGroups


* **功能描述**

　　ModifyInstanceGroups用于修改集群实例组的实例个数或实例组配置信息，如果修改了实例组个数集群就会进行相应的扩容或缩容。
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考2.2[公共参数](gong_gong_can_shu.md)
  
　　**ClusterId**
  
　　　　需要列出实例组信息的集群标识。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**InstanceGroups**
    
　　　　InstanceGroup类型列表。<br>
　　　　类型：InstanceGroup列表  (5.8 InstanceGroup)<br>
　　　　是否必须：是
    
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
X-Ksc-Target: ElasticMapReduce_V1.ModifyInstanceGroups
{
    "ClusterId": "e1b637b5-210d-45b3-bc16-0338b3c8cf8e",
    "InstanceGroups": [
        {
            "InstanceGroupId": "e1b637b5-210d-45b3-bc16-0338b3c8cf8e-gn-e51f56af-CORE",
            "InstanceCount": 3,
            "InstanceIdsToTerminate": []
        }
    ]
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 2
{}
```


