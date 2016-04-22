## InstanceGroupConfig

　　InstanceGroupType
  
　　　　实例组类型
　　　　类型：String
　　　　是否必须：是
　　　　合法值：MASTER、CORE、TASK
    
　　InstanceType
  
　　　　实例组中实例的配置类别（flavor信息）
　　　　类型：String
　　　　合法值：kmr.general、kmr.memory、kmr.storage、kmr.compute、kmr.general.2x、kmr.memory.2x、kmr.storage.2x、kmr.compute.2x
　　　　是否必须：是
    
　　InstanceCount
  
　　　　实例组中实例个数
　　　　类型：Integer
　　　　是否必须：是