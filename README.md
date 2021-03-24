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
                ```SYN_SENT/SYN_RCVD/ESTABLISHED```
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
            - RTT run-trip time
            - RTO
        - 拥塞控制（整个网络）
            - 拥塞避免
                - MSS max segment size
            - 慢开始
            - 快恢复
            - 快重传
            - 流量控制
            - 滑动窗口
        - 发送窗口和接收窗口(点对点)
- 应用层协议
    - HTTP
## 面向对象编程OOP
## 设计模式
## 多线程

## Java 基础
https://github.com/Snailclimb/JavaGuide#java
## 后台/系统开发技术
- Dubbo
- Springboot
- Springcloud
## 项目源码
## MySQL
- [顺丰快递：请签收MySQL灵魂十连 - 简书](https://www.jianshu.com/p/7193a037b4da)
- [面试官灵魂拷问：为什么 SQL 语句不要过多的 join？ - 知乎](https://zhuanlan.zhihu.com/p/338373021?utm_source=wechat_session&utm_medium=social&utm_oi=43355929051136&wechatShare=1&s_r=0)
- [https://blog.csdn.net/lilongsy/article/details/100558721](https://blog.csdn.net/lilongsy/article/details/100558721)
## 其他
- [HTTPS与SNI扩展，一个IP绑定多个SSL证书](https://www.ert7.com/service/knowledge/3999.html)
- [TCP会话劫持](https://mp.weixin.qq.com/s/U0tEoK7w5SRmBpjZM8fsXA)