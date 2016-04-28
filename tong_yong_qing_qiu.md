## 通用请求

* **[服务信息](fu_wu_xin_xi.md)**
* **[公共参数](gong_gong_can_shu.md)**
* **[签名机制](qian_ming_ji_zhi.md)**
* **[通用错误信息](tong_yong_cuo_wu_xin_xi.md)**


## 服务信息

* 服务地址
 
　　金山云KMR服务接入地址：
  
 　　•　北京地区：kmr.cn-beijing-6.api.ksyun.com <br/>
 　　•　上海地区：kmr.cn-shanghai-2.ksyun.com

* 通讯协议

　　只支持通过HTTP协议进行通信。

* 请求方法

　　支持HTTP POST方法发送请求。

* 请求参数

　　每个请求都需要指定要执行的操作，即X-Action参数（例如ListClusters），以及每个操作都需要包含的公共请求参数和指定操作所特有的请求参数。

* 编码方式

　　请求及返回结果都使用UTF-8字符集进行编码。

* 返回结果

　　仅支持json格式的返回结果。
