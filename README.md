# modbus_vcr
可支持ettercap0.8.3.1（目前的最新版）
这是 Ettercap 的一个简单插件，它利用了控制系统协议中缺乏数据完整性的问题。
这个 Ettercap 插件对 Modbus 系统执行 MITM 攻击。它记录 10 秒钟的 modbus 通信，然后用先前记录的响应覆盖控制系统网络上的未来状态数据。这有效地使控制系统操作员对其过程状态视而不见，同时使操作员相信状态更新仍在发生。
# 使用流程
1. 在plug-ins中创建一个文件夹，并在文件夹内创建一个.c文件
![image-20220710215142896](https://raw.githubusercontent.com/randomlifeme/clouding/master/img/image-20220710215142896.png)
2. 修改配置文件
![image-20220710215300709](https://raw.githubusercontent.com/randomlifeme/clouding/master/img/image-20220710215300709.png)
3. 编译源码
使用main.sh
首先chmod 777 main.sh，然后./main.sh执行，main.sh文件放到ettercap0.8.3.1主目录下
# 关键说明
modbus的协议识别是根据端口来的，所以如果端口不是默认的502端口，请修改
插件使用命令
```
ettercap -i eth1 -T -q -M ARP:remote -P modbus_vcr /ip1/ /ip2/
```
# 注明
代码仅用于学术交流，切勿用于非法操作
# 联系
如果你在使用过程中遇到问题，请联系我s1412154512@163.com
