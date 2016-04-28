## 数据类型

 　　KMR API使用了多种自定义数据类型，本章节将对这些数据类型做详细介绍
   
   
[**1. ClusterConfig**](ClusterConfig.md)

[**2. ClusterStatus**](ClusterStatus.md)

[**3. StepConfig**](StepConfig.md)

[**4. Step**](Step.md)

[**5. HadoopJarStepConfig**](HadoopJarStepConfig.md)
        
[**6. StepStatus**](StepStatus.md)

[**7. ClusterSummary**](ClusterSummary.md)

[**8. InstanceGroup**](InstanceGroup.md)

[**9. InstanceGroupStatus**](InstanceGroupStatus.md)

[**10. Instance**](Instance.md)

[**11. InstanceStatus**](InstanceStatus.md)

[**12. InstanceGroupConfig**](InstanceGroupConfig.md)

[**13. Configuration**](Configuration.md)

[**14. BootstrapAction**](BootstrapAction.md)
        
[**15. ScriptBootstrapAction**](ScriptBootstrapAction.md)
   

## ClusterConfig

　　**Applications**
  
　　　　集群安装的应用列表。<br>
　　　　类型：String列表<br>
　　　　可选值: 可选值为“hadoop”，“hive”，“pig”与“spark”，区分大小写。任何集群都会默认会带上“hadoop”<br>
　　　　是否必须：否
    
　　**AutoTerminate**
  
　　　　集群在运行完作业后是否自动释放。<br>
　　　　类型：Boolean <br>
　　　　是否必须：否
    
　　**DistributionVersion**
  
　　　　集群选用的Hadoop发行版本信息。现阶段均为“kmr-1.0.0”。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Id**
  
　　　　集群ID。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**InstanceAttributes**
  
　　　　集群主机的参数，现阶段为空。<br>
　　　　类型：String列表<br>
　　　　是否必须：否
    
　　**LogUri**
  
　　　　日志归集的KS3路径。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**MasterPublicIP**
  
　　　　如果集群创建Enable EIP，则为公网IP地址，否则为空。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　**　Name**
 
　　　　集群名称。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**NormalizedInstanceMins**
  
　　　　集群运行时间，从实例创建成功到集群释放，以分钟为单位。<br>
　　　　类型：Integer<br>
　　　　是否必须：否
    
　　**ServiceRole**
  
　　　　集群的IAM角色，现阶段金山云IAM还未正式完成，取得的值均为Null。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Status**
  
　　　　集群的IAM角色，现阶段金山云IAM还未正式完成，取得的值均为Null。<br>
　　　　类型：ClusterStatus  （[ClusterStatus](ClusterStatus.md)）<br>
　　　　是否必须：否
    
　　**TerminationProtected**
  
　　　　集群是否启用释放保护锁。<br>
　　　　类型：Boolean<br>
　　　　是否必须：否

　　**VpcDomainId**
  
　　　　集群所属的虚拟专有网络（VPC）信息。<br>
　　　　类型：String <br>
　　　　是否必须：否

　　**VpcSubnetId**
  
　　　　集群所属的虚拟专有网络（VPC）子网信息。<br>
　　　　类型：String <br>
　　　　是否必须：否

　　**VpcEndpointId**

　　　　集群所属的虚拟专有网络（VPC）的Endpoint子网信息，用于创建KMR部署使用的相关网络资源比如内网LB。<br>
　　　　类型：String <br>
　　　　是否必须：否
    
　　**Configurations**
  
　　　　集群配置信息<br>
　　　　类型：Configuration列表（[Configuration](Configuration.md)）<br>
　　　　是否必须：否
    
　　**BootstrapActions**
  
　　　　集群引导操作列表<br>
　　　　类型：BootstrapAction列表([BootstrapAction](BootstrapAction.md))<br>
　　　　是否必须：否
    
    
    ## ClusterStatus

　　**State**
  
　　　　集群状态。<br>
　　　　类型：String<br>
　　　　可选值：STARTING | RUNNING | TERMINATING | TERMINATED | TERMINATED_WITH_ERRORS<br>
　　　　是否必须：否
    
    
    
    ## StepConfig

　　**ActionOnFailure**
  
　　　　作业失败策略。<br>
　　　　类型：String<br>
　　　　可选值:  TERMINATE_JOB_FLOW | TERMINATE_CLUSTER | CANCEL_AND_WAIT | CONTINUE<br>
　　　　是否必须：否
    
　　**HadoopJarStep**
  
　　　　配置作业使用的jar file。<br>
　　　　类型：HadoopJarStepConfig（[HadoopJarStepConfig](HadoopJarStepConfig.md)）<br>
　　　　是否必须：是
    
　　**Name**
  
　　　　作业名称。<br>
　　　　类型：String<br>
　　　　长度限制：0-256<br>
　　　　是否必须：是
    
　　**Type**
  
　　　　作业类型。<br>
　　　　类型：String<br>
　　　　可选值：MapReduce | MapReduce.Streming | Pig | Hive | Spark<br>
　　　　是否必须：是
    
    
    ## Step

　　**ActionOnFailure**
  
　　　　作业失败策略。<br>
　　　　类型：String<br>
　　　　可选值:  TERMINATE_JOB_FLOW | TERMINATE_CLUSTER | CANCEL_AND_WAIT | CONTINUE<br>
　　　　是否必须：否
    
　　**HadoopJarStep**
  
　　　　配置作业使用的jar file。<br>
　　　　类型：HadoopJarStepConfig （[HadoopJarStepConfig](HadoopJarStepConfig.md)）<br>
　　　　是否必须：否
    
　　**Name**
  
　　　　作业名称。<br>
　　　　类型：String<br>
　　　　长度限制：0-256<br>
　　　　是否必须：否
 
　　**Type**
  
　　　　作业类型。<br>
　　　　类型：String<br>
　　　　可选值：MapReduce、MapReduce.Streming、Pig、Hive、Spark<br>
　　　　是否必须：是
    
　　**Id**
  
　　　　作业ID。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Status **
  
　　　　作业状态。<br>
　　　　类型：StepStatus  （[StepStatus](StepStatus.md)）<br>
　　　　是否必须：否
    
    
    ## HadoopJarStepConfig

　　**Args**
  
　　　　指定命令行列表传递给jar file的main函数。<br>
　　　　类型：String列表<br>
　　　　是否必须：否
    
　　**Jar**
  
　　　　指定作业的jar file路径。<br>
　　　　类型：String<br>
　　　　是否必须：是
    
　　**MainClass**
  
　　　　指定jave file中main classs名称。如果没有指定，jar file需要在manifest文件中指定。<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Properties**
  
　　　为作业运行指定key-value列表，你可以在你的主函数中使用这些key-value。<br>
　　　类型：KeyValue 列表<br>
　　　是否必须：否