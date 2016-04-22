## StepConfig

　　**ActionOnFailure**
  
　　　　作业失败策略。<br>
　　　　类型：String<br>
　　　　可选值:  TERMINATE_JOB_FLOW | TERMINATE_CLUSTER | CANCEL_AND_WAIT | CONTINUE<br>
　　　　是否必须：否
    
　　**HadoopJarStep**
  
　　　　配置作业使用的jar file。<br>
　　　　类型：HadoopJarStepConfig（5.5 HadoopJarStepConfig）<br>
　　　　是否必须：是
    
　　**Name**
  
　　　　作业名称。<br>
　　　　类型：String<br>
　　　　长度限制：0-256<br>
　　　　是否必须：是