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
　　　　类型：ClusterConfig  （5.1 [ClusterConfig](ClusterConfig.md)） 

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
X-Action: DescribeCluster
X-Version: 2016-05-20
{
    "ClusterId": "ffd8270a-48e0-4f68-8a35-0f8562302ad6"
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: xxx
{
  "InstanceAttributes": [],
  "Name": "lxk-quota-test-0",
  "ServiceRole": null,
  "TerminationProtected": false,
  "HadoopVersion": "hadoop 2.6.0",
  "LogUri": "ks3://kmrhkbj/lxk-log",
  "AutoTerminate": false,
  "Status": {
    "State": "RUNNING"
  },
  "MasterPublicDnsName": "120.168.113.60",
  "NormalizedInstanceMins": 1333,
  "Applications": [
    "hadoop"
  ],
  "Id": "ffd8270a-48e0-4f68-8a35-0f8562302ad6"
}
```


