## 为集群添加SSH密钥

KMR集群仅支持SSH 密钥认证方式，在使用SSH之前，您需要为集群添加SSH密钥。

1.使用密钥生成工具生成SSH-2 RSA密钥，保存好私钥和公钥

windows用户可以使用PuTTYgen.exe工具http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html
Linux 用户可以通过 ssh-keygen –t rsa 来生成，默认生成在~/.ssh/目录下，公钥文件是~/.ssh/id_rsa.pub，用户使用ssh-keygen时也可以自己指定公钥目录。


2.打开KMR控制台，选择“密钥管理”，点击“SSH密钥”按钮点击“创建密钥”按钮，把第1步生成的公钥文件内容粘贴到对话框，并点击“创建”


3.选择刚刚创建好的密钥，点击“加载到集群”按钮，把密钥加载到集群，您可以把密钥同时加载到多个集群。至此，密钥加载完成。