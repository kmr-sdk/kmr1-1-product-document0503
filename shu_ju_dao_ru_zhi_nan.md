## 数据导入指南

　**　1. 数据导入到KS3**

　　KMR集群可以直接访问标准存储服务KS3，在开始使用KMR之前，我们建议您开通KS3服务，把计算程序和原始数据集中到KS3中便于管理和持久化保存。
  
　　（1）进入KS3控制台，新建存储空间 http://ks3.ksyun.com/console.html#/
  
  ![数据导入1](./images/sjdr1.png)
  
　　（2）“地区”选择“中国（北京）”（目前KMR仅在北京region提供），输入空间名称，如无需公开读写，访问控制选择“私密”即可。
  
  ![数据导入2](./images/sjdr2.png)
  
  
  
  （2）进入空间，选择“内容管理”，可以创建目录，或者直接通过浏览器上传文件，超过500M以上的文件可以使用SDK或者工具上传
KS3 SDK:     https://github.com/ks3sdk
KS3上传工具 http://www.ksyun.com/doc/art/id/432
  
  