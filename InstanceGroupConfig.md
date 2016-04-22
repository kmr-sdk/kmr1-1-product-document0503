## InstanceGroupConfig

　　**InstanceGroupType**
  
　　　　实例组类型<br>
　　　　类型：String<br>
　　　　是否必须：是<br>
　　　　合法值：MASTER、CORE、TASK
    
　　**InstanceType**
  
　　　　实例组中实例的配置类别（flavor信息）<br>
　　　　类型：String<br>
　　　　合法值：kmr.general | kmr.memory | kmr.storage | kmr.compute | kmr.general.2x | kmr.memory.2x | kmr.storage.2x | kmr.compute.2x<br>
　　　　是否必须：是
    
　　**InstanceCount**
  
　　　　实例组中实例个数<br>
　　　　类型：Integer<br>
　　　　是否必须：是