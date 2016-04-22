## JobFlowInstancesConfig

　　**KeepJobFlowAliveWhenNoSteps**
  
　　　　集群在运行完作业后是否自动释放。<br>
　　　　类型：Boolean <br>
　　　　是否必须：否
    
　　**TerminationProtected**
  
　　　　集群是否启用释放保护锁。<br>
　　　　类型：Boolean<br>
　　　　是否必须：否
    
　　**InstanceGroups**
  
　　　　集群实例组配置信息。<br>
　　　　类型：InstanceGroupConfig 5.13 InstanceGroupConfig<br>
　　　　是否必须：是
