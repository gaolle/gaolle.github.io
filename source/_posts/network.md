# 物理层

# 数据链路层

## 点对点信道

### 封装成帧

* 帧定界

### 透明传输

* 字节填充

### 差错检测

* 比特差错

* 循环冗余检验CRC
* 凡是接收端数据链路层接受的帧均无差错

### 点对点协议PPP

* 不支持多点线路，只支持点对点的链路通信
* 只支持全双工链路
* 零比特填充实现透明传输

## 广播信道







# notes

* 路由器转发分组时使用的协议栈只有下三层
* 网络适配器包括数据链路层和物理层的功能
* 网络层协议数据单元是IP数据报
* MTU(最大传送单元)- 所能传送的**帧的数据部分**最长上限-1500字节