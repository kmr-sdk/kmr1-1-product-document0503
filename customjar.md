## 添加Custom JAR作业

　　您可以编写 Java 应用程序，生成 JAR 文件，然后将 JAR 文件上传到集群本地HDFS或者KS3中来处理数据。当执行此操作时，JAR 文件必须包含适用于 Map-Reduce 功能的实现。
  
　　1.在KMR集群创建时或者创建完成后打开添加作业页面，前置步骤请参考　[创建集群-快速选项](chuang_jian_ji_qun_kuai_su_xuan_xiang.md)、[创建集群-高级选项](chuang_jian_ji_qun_gao_ji_xuan_xiang.md) 和　[查看作业](zuo_ye_xiang_qing.md)

![custom jar](./images/customjar.png)

　　2.在添加作业页面填写作业信息，点击确定提交：