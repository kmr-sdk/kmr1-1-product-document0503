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
  
　　　　集群选用的Hadoop发行版本信息。现阶段均为“kmr-1.0.0
”。<br>
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
    
　　**MasterPublicDnsName**
  
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
　　　　类型：ClusterStatus  （5.2 [ClusterStatus](ClusterStatus.md)）<br>
　　　　是否必须：否
    
　　**TerminationProtected**
  
　　　　集群是否启用释放保护锁。<br>
　　　　类型：Boolean<br>
　　　　是否必须：否
    
　　**Configurations**
  
　　　　集群配置信息<br>
　　　　类型：Configuration列表（5.14 [Configuration](Configuration.md)）<br>
　　　　是否必须：否
    
　　**BootstrapActions**
  
　　　　集群引导操作列表<br>
　　　　类型：BootstrapAction列表(5.15 [BootstrapAction](BootstrapAction.md))<br>
　　　　是否必须：否