## LaunchCluster


* **功能描述**

　　创建集群操作，操作成功后会创建一个KMR集群，如果参数中带有作业配置，则集群创建成功后将自动运行指定的作业。如果AutoTerminate设置为True，则作业运行完毕后集群不会释放，反之集群会在所有作业完成后自动释放；关于参数中TerminationProtected的设置及原理介绍请参见SetTerminationProtection部分。
 
* **请求参数**

　　关于所有操作使用的通用参数信息，请参考[公共参数](gong_gong_can_shu.md)
  
　　**DistributionVersion**
  
　　　　Hadoop发行版本说明。当前仅支持“hadoop 2.6.0”，如果不填则默认试用“hadoop 2.6.0”。　<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Applications.member.N**
  
　　　　安装应用列表。可选值为“hadoop”，“hive”，“pig”与“spark”，区分大小写。如果不填则默认为“hadoop”。<br>
　　　　类型：String列表<br>
　　　　是否必须：否
    
　　**InstanceGroups.member.N**
  
　　　　集群里虚机的配置和数目信息。<br>
　　　　类型：InstanceGroupConfig列表   ([InstanceGroupConfig](InstanceGroupConfig.md))<br>
　　　　是否必须：是
   
　　**AutoTerminate**
  
　　　　集群在运行完作业后是否自动释放。<br>
　　　　类型：Boolean <br>
　　　　是否必须：否
   
　　**TerminationProtected**
  
　　　　集群是否启用释放保护锁。<br>
　　　　类型：Boolean <br>
　　　　是否必须：否
   
　　**VpcDomainId**
  
　　　　集群所属的虚拟专有网络（VPC）信息。<br>
　　　　类型：String <br>
　　　　是否必须：是

　　**VpcSubnetId**
  
　　　　集群所属的虚拟专有网络（VPC）子网信息。<br>
　　　　类型：String <br>
　　　　是否必须：是

　　**VpcEndpointId**

　　　　集群所属的虚拟专有网络（VPC）的Endpoint子网信息，用于创建KMR部署使用的相关网络资源比如内网LB。<br>
　　　　类型：String <br>
　　　　是否必须：是
   
　　**LogUri**
  
　　　　日志输出的KS3路径，格式为：“KS3://bucket/object_key”。如果不填则日志不会输出到KS3。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Name**
  
　　　　集群的名称。仅支持大小写字母、数字、减号和下划线。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**Steps.member.N**
  
　　　　自定义需要运行的作业列表。<br>
　　　　类型：StepConfig列表 （[StepConfig](StepConfig.md)）<br>
　　　　是否必须：否
    
　　**EnableEIP**
  
　　　　是否启用eip信息，如果设置为True，则集群的Master节点会被分配一个外网ip，默认为False。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Configurations.member.N**
  
　　　　所创建集群的配置信息。<br>
　　　　类型：Configuration列表 （[Configuration](Configuration.md)）<br>
　　　　是否必须：否
    
　　**BootstrapActions.member.N**
  
　　　　集群引导操作列表<br>
　　　　类型：BootstrapAction列表([BootstrapAction](BootstrapAction.md))<br>
　　　　是否必须：否
    　　
* **返回参数**

　　返回结果包含以下字段：
  
　　**ClusterId**
  
　　　　创建成功的集群ID<br>
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
X-Action: LaunchCluter
X-Version: 2016-05-20
{
  "Name": "api-test",
  "KeepJobFlowAliveWhenNoSteps": False
  "InstanceGroups" : [
      {
        "InstanceType" : "kmr.general",
        "InstanceCount" : 1,
        "InstanceGroupType" : "MASTER"
      },
      {
        "InstanceType" : "kmr.general",
        "InstanceCount" : 2,
        "InstanceGroupType" : "CORE"
      }
  ],
  "Steps": [
        {
            "ActionOnFailure": "CONTINUE",
            "Name": "java_test",
            "HadoopJarStep": {
                "Args": [
                    "ks3://kmr-bj-test/input",
                    "ks3://kmr-bj-test/output"
                ],
                "Jar": "ks3://kmr-bj-test/jobtest/job.jar",
                "MainClass": "org.apache.hadoop.examples.WordCount"
            }
        }
    ]
}
```


　　**返回样例**
  
```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: xxx
{
  "ClusterId": "ffd8270a-48e0-4f68-8a35-0f8562302ad6"
}
```


