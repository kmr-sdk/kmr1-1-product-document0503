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
  
　　　　指定jave file中main classs名称。如果没有指定，jar file需要在manifest文件中指定。
　　　　类型：String
　　　　是否必须：否
    
　　**Properties**
  
　　　为作业运行指定key-value列表，你可以在你的主函数中使用这些key-value。
　　　类型：KeyValue 列表
　　　是否必须：否