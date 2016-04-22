## Configuration

　　所创建集群的配置信息。
  
　　**Classification**
  
　　　　配置信息类别<br>
　　　　类型：String<br>
　　　　是否必须：否<br>
　　　　可选值：
    
|Classification|	FileName|
|:|:|
|core-site|	core-site.xml|
|hdfs-site |	hdfs-site.xml|
|mapred-site|	mapred-site.xml|
|yarn-site	|yarn-site.xml|
|capacity-scheduler|	capacity-scheduler.xml|
|hadoop-env	|hadoop-env.sh|
|httpfs-env.sh|	httpfs-env.sh|
|mapred-env|	mapred-env.sh|
|yarn-env	|yarn-env.sh|
|hadoop-log4j	|log4j.properties|
|hive-env	|hive-env.sh|
|hive-site|	hive-site.xml|
|hive-exec-log4j|	hive-exec-log4j.properties|
|hive-log4j	|hive-log4j.properties|
|spark-env|	spark-env.sh|
|spark-defaults|	spark-defaults.conf|
|spark-log4j|	log4j.properties|
|httpfs-site|	httpfs-site.xml|

　　**Properties**
  
　　　　配置信息属性和值的集合<br>
　　　　Type：map\<string,string\>　　　
       
　　**Configurations**
  
　　　　Configuration列表<br>
　　　　类型：Configuration列表<br>
　　　　是否必须：否
    
　　Configuration类型数据示例：


```{
"Configurations": [
{
     "Classification":"yarn-env",
     "Configurations": [
      {
         "Classification":"export",
         "Properties":{
                  "YARN_NODEMANAGER_OPTS":" -Xmx2049m"
         }
     }
]
 },
 {
     "Classification":"mapred-site",
     "Properties":{
         "mapred.tasktracker.map.tasks.maximum":"5"
      }
 }
]
}

```