## ClusterConfig

　　Applications
　　　　集群安装的应用列表。
　　　　类型：String列表
　　　　可选值: 可选值为“hadoop”，“hive”，“pig”与“spark”，区分大小写。任何集群都会默认会带上“hadoop”
　　　　是否必须：否
　　AutoTerminate
　　　　集群在运行完作业后是否自动释放。
　　　　类型：Boolean 
　　　　是否必须：否
　　HadoopVersion
　　　　集群选用的Hadoop发型版本信息。现阶段均为“hadoop 2.6.0”。
　　　　类型：String
　　　　是否必须：否
　　Id
　　　　集群ID。
　　　　类型：String
　　　　是否必须：否
　　InstanceAttributes
　　　　集群主机的参数，现阶段为空。
　　　　类型：String列表
　　　　是否必须：否
　　LogUri
　　　　日志归集的KS3路径。
　　　　类型：String
　　　　是否必须：否
　　MasterPublicDnsName
　　　　如果集群创建Enable EIP，则为公网IP地址，否则为空。
　　　　类型：String
　　　　是否必须：否
　　Name
　　　　集群名称。
　　　　类型：String
　　　　是否必须：否
　　NormalizedInstanceMins
　　　　集群运行时间，从实例创建成功到集群释放，以分钟为单位。
　　　　类型：Integer
　　　　是否必须：否
　　ServiceRole
　　　　集群的IAM角色，现阶段金山云IAM还未正式完成，取得的值均为Null。
　　　　类型：String
　　　　是否必须：否
　　Status
　　　　集群的IAM角色，现阶段金山云IAM还未正式完成，取得的值均为Null。
　　　　类型：ClusterStatus  （5.2 ClusterStatus）
　　　　是否必须：否
　　TerminationProtected
　　　　集群是否启用释放保护锁。
　　　　类型：Boolean
　　　　是否必须：否
　　Configurations
　　　　集群配置信息
　　　　类型：Configuration列表（5.14 Configuration）
　　　　是否必须：否
　　BootstrapActions
　　　　集群引导操作列表
　　　　类型：BootstrapAction列表(5.15 BootstrapAction)
　　　　是否必须：否