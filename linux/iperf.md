> iperf命令是一个网络性能测试工具。iperf可以测试TCP和UDP带宽质量。iperf可以测量最大TCP带宽，具有多种参数和UDP特性。iperf可以报告带宽，延迟抖动和数据包丢失。利用iperf这一特性，可以用来测试一些网络设备如路由器，防火墙，交换机等的性能。

> [参考](http://man.linuxde.net/iperf)

> 默认端口 5001 

UDP模式
----

服务器端：

    iperf -u -s
客户端：

    iperf -u -c 192.168.1.1 -b 100M -t 60
在udp模式下，以100Mbps为数据发送速率，客户端到服务器192.168.1.1上传带宽测试，测试时间为60秒。

    iperf -u -c 192.168.1.1 -b 5M -P 30 -t 60
客户端同时向服务器端发起30个连接线程，以5Mbps为数据发送速率。

    iperf -u -c 192.168.1.1 -b 100M -d -t 60 -p 5001
    
以100M为数据发送速率，进行上下行带宽测试。


TCP模式
----

服务器端：

    iperf -s
客户端：

    iperf -c 192.168.1.1 -t 60
在tcp模式下，客户端到服务器192.168.1.1上传带宽测试，测试时间为60秒。

    iperf -c 192.168.1.1  -P 30 -t 60
客户端同时向服务器端发起30个连接线程。

    iperf -c 192.168.1.1  -d -t 60
进行上下行带宽测试。