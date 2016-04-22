## InstanceGroup

　　**Id**
  
　　　　实例组Id<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Name**
  
　　　　实例组名<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**InstanceGroupType**
  
　　　　实例组类型<br>
　　　　类型：String<br>
　　　　是否必须：否<br>
　　　　合法值：MASTER、CORE、TASK
    
　　**InstanceType**
  
　　　　实例组中实例的配置类别（flavor信息）<br>
　　　　类型：String<br>
　　　　合法值：kmr.general、kmr.memory、kmr.storage、kmr.compute、kmr.general.2x、kmr.memory.2x、kmr.storage.2x、kmr.compute.2x<br>
　　　　是否必须：否
    
　　**InstanceCount**
  
　　　　实例组中实例个数<br>
　　　　类型：Integer<br>
　　　　是否必须：否
    
　　**Status**
  
　　　　实例组状态<br>
　　　　类型：InstanceGroupStatus  （5.9 InstanceGroupStatus）<br>
　　　　是否必须：否
    
　　**Configurations**
  
　　　　实例组配置信息，可以针对每个实例组单独设置配置项<br>
　　　　类型：Configuration列表（5.14 Configuration）<br>
　　　　是否必须：否