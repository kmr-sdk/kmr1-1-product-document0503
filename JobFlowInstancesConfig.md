## JobFlowInstancesConfig

　　KeepJobFlowAliveWhenNoSteps
  
　　　　集群在运行完作业后是否自动释放。
　　　　类型：Boolean 
　　　　是否必须：否
    
　　TerminationProtected
  
　　　　集群是否启用释放保护锁。
　　　　类型：Boolean
　　　　是否必须：否
    
　　InstanceGroups
  
　　　　集群实例组配置信息。
　　　　类型：InstanceGroupConfig 5.13 InstanceGroupConfig
　　　　是否必须：是
