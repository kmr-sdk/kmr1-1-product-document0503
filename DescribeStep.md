## DescribeStep


* **功能描述**

　　查询指定集群中一个指定作业的详细信息
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考2.2[公共参数](gong_gong_can_shu.md)
  
　　**ClusterId**
  
　　　　需要查询的集群ID。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**StepId**
  
　　　　需要列出的作业ID<br>
　　　　类型：Sting<br>
　　　　是否必须：是

    
* **返回参数**

　　返回结果包含以下字段：
  
　　**Step**
  
　　　　需要查询作业的详细信息。<br>
　　　　类型：Step （5.4 Step）
    
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
X-Ksc-Target: ElasticMapReduce_V1.DescribeStep
{
    "ClusterId": "366bb23b-ef63-494d-acb8-3d26d6375da9",
    "StepId": "56964e88c-cb6e-4592-be97-53a5e2a2bfde"
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 2
{
    "Step": {
            "Status": {
                "State": "RUNNING"
            },
"HadoopJarStep": {
                "Args": [
                    "-input",
                    "ks3://yourbucket/input",
"-output",
"ks3://yourbucket/output",
"-mapper",
"ks3://yourbucket/mapper.py",
                  "-reducer"
"ks3://yourbucket/reducer.py",
"-numMapTasks",
                    "1",
                    "-numReduceTasks",
                    "1",
                    "-args",
                    ""
                ],
                "Jar": "ks3://kmr/libs/hadoop-streaming.jar",
                "Properties": {}
            },
"Name": "streaming-type-job"
            "ActionOnFailure": "CONTINUE",
            "Id": "56964e88c-cb6e-4592-be97-53a5e2a2bfde"
    }
}
```


