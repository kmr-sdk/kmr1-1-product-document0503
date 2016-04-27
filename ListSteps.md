## ListSteps


* **功能描述**

　　列出指定集群的作业状态信息，允许您基于特定的条件对这些信息进行筛选；例如，基于作业状态筛选。每次调用默认返回100个作业，每次最多返回100个，同时会返回一个Marker来对多次ListSteps请求调用进行分页跟踪。
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考[公共参数](gong_gong_can_shu.md)
  
　　**ClusterId**
  
　　　　需要查询的集群ID。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**StepIds**
  
　　　　需要列出的作业ID，用于过滤条件。<br>
　　　　类型：Sting列表<br>
　　　　是否必须：否

　　**StepStates.member.N**
  
　　　　需要列出的集群状态。<br>
　　　　类型：String列表<br>
　　　　可选值：PENDING | RUNNING | COMPLETED | CANCELLED | FAILED | INTERRUPTED | TRANSFERINGLOG <br>
　　　　是否必须：否
    
　　**Marker**
  
　　　　分页标识。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
* **返回参数**

　　返回结果包含以下字段：
  
　　**Steps**
  
　　　　满足请求中给出的过滤条件的作业列表。<br>
　　　　类型：Step列表 （[Step](Step.md)）
    
　　**Marker**
  
　　　　用于获取下一页结果集的分页标识。<br>
　　　　类型：String

* **错误信息**

　　关于所有操作使用的通用错误信息，参考[通用错误信息](tong_yong_cuo_wu_xin_xi.md)

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
X-Action: ListSteps
X-Version: 2016-05-20
{
    "StepStates": ["RUNNING", "PENDING"]
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: xxx
{
    "Marker": null,
    "Steps": [
        {
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
            "DurationMins": 2,
            "Name": "streaming-type-job"
            "ActionOnFailure": "CONTINUE",
            "StepType": "MapReduce",
            "Id": "56964e88c-cb6e-4592-be97-53a5e2a2bfde",
            "CreatedAt": "2016-01-08T12:10:07"
        }
    ]
}
```


