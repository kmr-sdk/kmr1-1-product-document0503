## 密钥管理指南


　　用户除了通过控制台来管理集群和作业外，也可以通过SSH来访问管理集群，而KMR集群仅支持SSH 密钥认证方式，因此密钥管理模块用来管理通过SSH方式访问集群的密钥。

* [创建密钥](chuang_jian_mi_yao.md)

* [密钥列表](mi_yao_lie_biao.md)


## 创建密钥

　　打开金山云控制台，选择KMR服务，选择“集群密钥”，点击“创建密钥”，进入创建密钥页面

![创建密钥](http://kmr-bj.ks3-cn-beijing.ksyun.com/doc_pic/mygl1.png)

| 字段 | 操作 |
| -- | -- |
| **名称** | 您可以为密钥输入描述性名称 |
| **描述** | 输入对该密钥的描述语言 |
| **公钥** | 输入用密钥生成工具生成的公钥，格式形如“ssh-rsaAAAAB3NzaC1yc2EAAAABJQAAAQEAxljLUF//ygzu1Dy/sArs1hpoN……”详情见 [为集群添加SSH密钥](tian_jia_ssh_mi_yao.md) |

