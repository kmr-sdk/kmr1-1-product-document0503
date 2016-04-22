## BootstrapAction

　　**Name**

　　　　引导操作名字　<br>
　　　　类型：string<br>
　　　　是否必须：是
    
　　**NodeGroups**
  
　　　　引导操作运行的实例组类型<br>
  　　　类型：string列表，合法值有：MASTER、CORE、TASK<br>
　　　　是否必须：否，如果不填默认在所有节点上都运行
    
　　**ScriptBootstrapAction**
  
　　　　引导操作脚本配置<br>
　　　　类型：ScriptBootstrapActive<br>
　　　　是否必须：是