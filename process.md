### 协议和架构部分
1. `ds.hpp`包括`AppPacket`，`SecPacket`和`PacketCTX`的主要结构和函数
2. `user.hpp`主要包括user类定义的功能函数
3. `utils.h`主要包括的是一些文件名的宏定义，可忽略
4. `crypto.h`中是关于AES，SM4和IBE的长度定义

### 通信打包部分
1. 发送从`packet_send.cpp`中出发依次进行`send_ap`，`send_sign`(签名)，`send_enc`(加密)，最后`send_sp`
2. 接收从`packet_handle.cpp`中出发依次进行`handle_ap`，`handle_verify`(验证)，`handle_dec`(解密)，最后`handle_sp`

### 前端功能选择部分
主要是通过`ui.cpp`文件进入，然后通过case转到不同的函数中