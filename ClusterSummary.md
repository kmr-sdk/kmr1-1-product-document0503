## ClusterSummary

　　**Id**
  
　　　　集群的唯一标识符，通常为UUID格式<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**Name**
  
　　　　集群名称<br>
　　　　类型：String<br>
　　　　是否必须：否
    
　　**NormalizedInstanceMins**
  
　　　　集群运行的分钟数。如果集群已经结束，则计时断为创建时间至释放时间；如果集群尚未结束，则为创建时间至现在的分钟数。本时间只是对集群运行时间的预估，并不反应实际记费时间。<br>
　　　　类型：Integer<br>
　　　　是否必须：否
    
　　**Status**
  
　　　　集群当前的状态信息<br>
　　　　类型：ClusterStatus<br>
　　　　是否必须：否