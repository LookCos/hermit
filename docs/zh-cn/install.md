#### 下载与安装  
Github release [https://github.com/LookCos/hermit/releases](https://github.com/LookCos/hermit/releases)  
蓝奏云 [https://wwi.lanzous.com/ipGqYmg1z0j](https://wwi.lanzous.com/ipGqYmg1z0j)

#### 简单设置  
##### 1. 安卓设备与电脑处于同一局域网:  
API的地址就是安卓设备在局域网中的地址，例如 `192.168.1.115`。  
此时我们打开浏览器输入`http://192.168.1.115:9999/`，当看到如下内容就说明运行成功,可以使用py-hermit或调用API来操作安卓设备了。
```json
{"code":0,"msg":"Hermit is ok!"}
```

##### 2. 模拟器用户。  
需要做一次端口映射，打开终端执行如下操作：   
```bash
# 通过adb 连接模拟器 （根据模拟器不同，注意端口有所不同，常见的有7555，5555）
adb connect 127.0.0.1:7555
# 将模拟器的9999端口转发到本机的 9999端口  
adb forward tcp:9999 tcp:9999
# 看到返回 9999， 就是成功了。这个时候，我们打开 127.0.0.1:9999 就能访问了
```

![](https://www.lookcos.cn/usr/uploads/2021/01/2021013111254293.png)
