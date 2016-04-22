## DescribeCluster


* **功能描述**

　　列出某个当前用户可见的集群详细信息，包括状态，硬件，软件设置等。
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考2.2[公共参数](gong_gong_can_shu.md)
  
　　**ClusterId**
  
　　　　需要列出实例组信息的集群标识。<br>
　　　　类型：String<br>
　　　　是否必须：是
    　　
* **返回参数**

　　返回结果包含以下字段：
  
　　**Cluster**
  
　　　　请求中集群的详细信息<br>
　　　　类型：ClusterConfig  （5.1 ClusterConfig） 

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
Content-Length: 186
Date: Thu, 07 Jan 2016 02:57:57 GMT
{
  "Marker": null,
  "Instances": [
    {
      "Status": {
        "State": "RUNNING"
      },
      "Id": "079d2b1f-cb1f-4365-acbb-c1b3f7424831",
      "PrivateIpAddress": "10.168.113.134",
      "PublicIpAddress": "10.168.113.134"
    }
  ]
}
```


