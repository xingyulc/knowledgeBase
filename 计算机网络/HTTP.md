# HTTP

3项WWW构建技术：把 SGML（Standard Generalized Markup Language，标准通用标记语言）作为页面的文本标记语言的 HTML（HyperText Markup Language，超文本标记语言）； 作为文档传递协议的 HTTP ；指定文档所在地址的 URL（Uniform12Resource Locator，统一资源定位符）

## TCP/IP

网络是在TCP/IP协议族上运作的。HTTP是TCP/IP上的一个子集。

### TCP/IP通信

![](E:\knowledgeBase\计算机网络\images\TCPIP通信2.png)

1. 发送端的客户端在应用层 （HTTP 协议）发出一个想看某个 Web 页面的 HTTP 请求。
2. 在传输层（TCP 协议）把从应用层处收到的数据（HTTP 请求报文）进行分割，并在各个报文上打上标记序号及端 口号后转发给网络层。
3. 在网络层（IP 协议），增加作为通信目的地的 MAC 地址后转发给链路层。这样一来，发往网络的通信请求就准备齐全了。
4. 接收端的服务器在链路层接收到数据，按序往上层发送，一直到应用 层。当传输到应用层，才能算真正接收到由客户端发送过来的 HTTP 请求。

### IP、TCP、DNS

#### IP

IP协议的作用就是将各种数据包传送给对方。而要确保数据准确传送给对方就要确保IP地址和MAC地址。

IP地址指明了节点被分配的地址。MAC地址是网卡所属的固定地址。IP间的通信依赖MAC地址。

ARP是一种地址解析协议，通过ARP解析IP地址可以得到MAC地址。

#### TCP

TCP位于传输层，提供可靠的字节流服务。

字节流：为了方便运输将大块的数据分割成报文段的数据包进行管理。

#### 三次握手确保数据能准确到达目标

![](E:\knowledgeBase\计算机网络\images\三次握手.png)

1、客户端发送SYN=1（表示请求连接），并发送一个seq（随机码）

2、服务器由于收到SYN=1，知道是请求连接，返回一个请求连接SYN=1和一个ack=seq+1（客户端随机码应答），且自己也返回一个seq（随机码）

3、客户端收到服务器的ack后验证，向服务器确认包发送ack=seq+1（服务器随机码应答）

图解http  p25

