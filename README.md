### install ss
```
 git clone https://github.com/suniceman/ss-fly
 ss-fly/ss-fly.sh -i jsonlocker 1024
```
option:

```
 启动：/etc/init.d/ss-fly start
 停止：/etc/init.d/ss-fly stop
 重启：/etc/init.d/ss-fly restart
 状态：/etc/init.d/ss-fly status
 查看ss链接：ss-fly/ss-fly.sh -sslink
 修改配置文件：vim /etc/shadowsocks.json
 ```
 
 ### install ssr
 ```
 git clone https://github.com/suniceman/ss-fly
 ss-fly/ss-fly.sh -ssr
 ```
 
 option:
 ```
 启动：/etc/init.d/shadowsocks start
 停止：/etc/init.d/shadowsocks stop
 重启：/etc/init.d/shadowsocks restart
 状态：/etc/init.d/shadowsocks status
 配置文件路径：/etc/shadowsocks.json
 日志文件路径：/var/log/shadowsocks.log
 代码安装目录：/usr/local/shadowsocks
```
uninstall:
```
./shadowsocksR.sh uninstall
```

# 一键开启BBR加速
BBR支持4.9以上的，如果低于这个版本则会自动下载最新内容版本的内核后开启BBR加速并重启，如果高于4.9以上则自动开启BBR加速，执行如下脚本命令即可自动开启BBR加速：
```
ss-fly/ss-fly.sh -bbr
```
装完后需要重启系统，输入y即可立即重启，或者之后输入reboot命令重启。

判断BBR加速有没有开启成功。输入以下命令：
```
sysctl net.ipv4.tcp_available_congestion_control
```
返回以下则成功
```
net.ipv4.tcp_available_congestion_control = bbr cubic reno
```
