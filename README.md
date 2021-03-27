美团对系统/后台开发工程师候选人重点考核的专业知识及专业技能计算机基础扎实，熟悉计算机相关的知识包括
- **数据结构、算法、操作系统、计算机网络、面向对象编程、设计模式、多线程**等等。
- Coding能力，**掌握**至少一门开发语言（Java/C++等）。
- 了解常见的**后台/系统开发技术**，最好阅读过一些项目的源码。

## 资料库
- [后端技术栈](https://github.com/linw7/Skill-Tree)
- [Java技术笔记](https://github.com/CyC2018/CS-Notes)
- [大厂面试题 2021](https://github.com/0voice/interview_internal_reference/blob/master/README.md)
- [美团技术团队](https://tech.meituan.com/2020/03/26/meituan-tech-corporate-recruitment.html)
- [某学渣の后台秋招日记](https://zhuanlan.zhihu.com/p/237740524?utm_source=wechat_session&utm_medium=social&s_r=0)
- [红衫](https://github.com/scdt-china/interview-assignments)
- [工具书全集](https://github.com/EbookFoundation/free-programming-books/blob/master/books/free-programming-books-zh.md)
- [并发编程网](http://ifeve.com/)
- [牛客](https://www.nowcoder.com/)
- [互联网 Java 工程师进阶知识完全扫盲](https://github.com/doocs/advanced-java)
- [《JavaGuide 面试突击版》](https://github.com/Snailclimb/JavaGuide)
- [Markdown Online Editor](https://dillinger.io/)

## 数据结构
## 算法
- 哈希算法
## 操作系统
## 计算机网络
- [“三次握手，四次挥手”你真的懂吗？ - 知乎](https://zhuanlan.zhihu.com/p/53374516)
- [三次握手 - 面向信仰编程](https://draveness.me/tags/%E4%B8%89%E6%AC%A1%E6%8F%A1%E6%89%8B)
- [为什么 TCP 协议有粘包问题](https://draveness.me/whys-the-design-tcp-message-frame/)
- [为什么 TCP 协议有性能问题](https://draveness.me/whys-the-design-tcp-performance/)
- [为什么 TCP 协议有 TIME_WAIT 状态](https://draveness.me/whys-the-design-tcp-time-wait/)
- 传输层协议
    - UDP
    - TCP
        - 三次握手
            - 半连接队列
                - SYN flood
            - 连接建立过程状态机
                - ```SYN_SENT/SYN_RCVD/ESTABLISHED```
        - 全连接队列
        - 四次挥手
            - 半关闭状态
            - 连接关闭过程状态机
                ```
                FIN_WAIT_1  ->    CLOSE_WAIT
                FIN_WAIT_2  <-  
                            ...
                        TIME PERIOD  
                            ...       
                            <-    LAST_ACK
                TIME_WAIT   ->    CLOSED
                CLOSED
                ```
            - TIME_WAIT
                - MSL max segment lifetime
        - TCP报文段首部和数据部分
        - 可靠性传输
            - 校验和
            - AQR重传
            - RTT round-trip time
            - RTO re-transmission timeout
            - RTO = RTT<sub>s</sub>(RTT加权平均往返时间) + 4*RTT<sub>d</sub>(RTT偏差的加权平均值)
        - 滑动窗口
        - 拥塞控制（整个网络）
            - 拥塞避免
                - MSS max segment size
            - 慢开始 cwnd=1 
            - 快恢复
            - 快重传
        - 流量控制
            - 滑动窗口
            - 发送窗口和接收窗口(点对点)
- 应用层协议
    - HTTP
        - method
            - GET/HEADER/OPTIONS: 安全请求，因为不会篡改数据
            - POST/PUT/DELETE/PATCH：不安全
            - GET/DELETE: 幂等性
            - TRACE: 返回追踪路径
            - CONNECTION: 建立SSL（Security Socket Layer）安全套接层和TSL(Transmission Security Layer)传输安全层把通信内容加密后进行隧道传输。
        - 状态码
            - 1XX: 正在处理
            - 2XX：成功
            - 3XX: 重定向 配合响应报文头部字段Location使得浏览器把请求重定向给指定URL
            - 4XX: 客户端请求错误
            - 5XX：服务端内部错误
        - HTTP 1.1之前
            - 默认短连接 长连接需要 connection: keep-alive
        - HTTP 1.1之后
            - 流水线： 基于长连接，同时发出多个请求，不用等待
            - 默认长连接 关闭连接需要 connection: close
            - 增加 100 状态码
            - 增加 Cache-Control:max-age设置缓存失效时间
        - HTTP 2.0
            - 二进制分帧层
                - headers帧和data帧（二进制）
                - 一个tcp连接可以搭载多个stream（双向，并发）
                - 不同的帧可以搭载不同的流stream，同一条message的帧到达接收方时，重组成一条message
            - 服务器推送
                ```
                浏览器请求某个路径下的资源时，允许服务器同步推送同一目录下的其他相关资源（promise）
                ```
            - 首部压缩
                - 首部字段表：客户端和服务端同时维护一个首部字段表，避免重复发送。
                - Huffman编码对首部字段进行压缩
    - HTTPS
        - SSL： 相比HTTP加了SSL安全套接层使数据传输更具安全性。
        - 加密
            - 混合加密 
                ```
                用非对称密钥来加密对称加密公钥，让公钥能够安全传输给服务器，后续使用对称密钥加密，提高加密解密的执行效率。
                ```
        - 认证
            - 证书签名
                ```
                浏览器访问装有证书的站点时，会向CA(Certificate Authority)申请证书，如果是可信赖的请求，CA会分配证书（签名+公钥）给站点，并且后续的请求会由CA进行签名，服务器收到请求之后，先认证这个请求是不是有CA的数字签名，认证通过后，用私钥解密获得请求实体。
                ```
        - 保证完整性
            - 报文摘要
                ```
                和MD5的区别：
                MD5加密的报文被篡改后，可以重新计算MD5值而不被发现。
                报文摘要即便被篡改，由于重新计算摘要需要明文，且解密成明文十分困难，加大了篡改成本。
                ```
    - Socket
        - I/O 模型
            - (sync&block)阻塞式 I/O （recvfrom期间不消耗cpu）
            - (sync&unblock)非阻塞式 I/O（询问消耗cpu）
            - (sync&block)复用/事件驱动 I/O（轮询）
            - (sync&unblock)信号驱动 I/O （sigaction系统发送SIGIO, cpu利用率相较前两种更高）
            - (async&unblock)异步 I/O （aio_read， 和信号驱动不同的是kernel在copy compelte后才发送信号）
        - sync和async的区别：在数据从kernel buff往application buff进行copy时（第二阶段)会不会阻塞住进程
        - block和unblock的区别：在等待I/O数据准备阶段（第一阶段)会不会阻塞
        
    - 代理
        - 正向代理
            - 为了解决访问不到而架设的请求跳转代理服务器，比如VPN，一般由客户端设置。
        - 反向代理
            - 为了隐藏真实IP、访问控制、访问日志管理、负载均衡、使用代理服务器的缓存功能而架设，如负载均衡器，一般由服务端设置。
## 面向对象编程OOP
## 设计模式
## 多线程

## Java 基础
https://github.com/Snailclimb/JavaGuide#java
## 应用范例
- SSO单点登录
- 短地址服务
## 后台/系统开发技术
- Dubbo
- Springboot
- Springcloud
- Kafka
- Docker K8S
- tcpdump/cap/
## 项目源码
## MySQL
- [顺丰快递：请签收MySQL灵魂十连 - 简书](https://www.jianshu.com/p/7193a037b4da)
- [面试官灵魂拷问：为什么 SQL 语句不要过多的 join？ - 知乎](https://zhuanlan.zhihu.com/p/338373021?utm_source=wechat_session&utm_medium=social&utm_oi=43355929051136&wechatShare=1&s_r=0)
- [https://blog.csdn.net/lilongsy/article/details/100558721](https://blog.csdn.net/lilongsy/article/details/100558721)
## 其他
- [HTTPS与SNI扩展，一个IP绑定多个SSL证书](https://www.ert7.com/service/knowledge/3999.html)
- [TCP会话劫持](https://mp.weixin.qq.com/s/U0tEoK7w5SRmBpjZM8fsXA)