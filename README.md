# CuteOne
**CuteOne**是一款OneDrive多网盘挂载程序，提供多盘负载，在线查看文件等功能。  
**希望有小伙伴能提供安装视频或图文文档，报酬是可以享用后续可能收费的扩展功能**  
**欢迎捐赠，QQ群：8331213**

* 首页
![](http://ww1.sinaimg.cn/large/a096a6bfly1g19wrs8zf6j21gt0qtdnl.jpg)

* 弹出层
![](http://ww1.sinaimg.cn/large/a096a6bfly1g19wsm3vzvj21gr0qogpi.jpg)

* 后台 - 驱动列表
![](http://ww1.sinaimg.cn/large/a096a6bfly1g19wtafu4uj21hc0ouq5m.jpg)

* 后台 - 主从网盘列表
![](http://ww1.sinaimg.cn/large/a096a6bfly1g19wtss2r4j21hc0ob407.jpg)

* 后台 - 设置
![](http://ww1.sinaimg.cn/large/a096a6bfly1g19wu2zmegj21hc0qq0uz.jpg)


# 环境需求
* Linux
* Nginx
* Python3  ——[如何安装Python3](https://www.cnblogs.com/s-seven/p/9105973.html)
* Mysql <= 5.7
* MongoDB


# 安装流程
* 前言
> 初次安装真的，我自己都觉得繁琐，但是一劳永逸；  
> 如果没有python3的，先安装python3 再执行下面的流程。
* 第一步，拉取代码  
```
git clone https://github.com/Hackxiaoya/CuteOne.git  
```
* 第二步，安装需求的库和创建uwsgi软连
```
pip3 install -r requirements.txt
ln -s /usr/local/python3/bin/uwsgi /usr/bin/uwsgi
```
* 第三步，启动网站后台运行  
```
nohup uwsgi --ini uwsgi.ini &
```
* 第四步，Nginx反代一下，端口是5000

* 第五步，访问安装路径
```
http://你的域名/install/
```
* 第六步，根据流程安装呗
```
等出现安装完成的字样就执行第七步
```
* 第七步，重启程序
```
killall -9 uwsgi && nohup uwsgi --ini uwsgi.ini &
```
* 第八步，添加驱动盘
```
http://你的域名/admin/
到驱动的位置添加个驱动，然后添加个网盘，然后更新一下缓存就可以了
```




# 常见问题
* 出现502 
> 大概是因为CuteOne没运行。
* 首次安装，访问报错
> 首次安装之后需要在后台先添加一个网盘才行。
* 启动了之后，访问报错
> 你大概是首次安装启动，请查看安装流程。



# 常见命令
* 查看uwsgi
```
pgrep -f uwsgi
```
* kill所有uwsgi
```
killall -9 uwsgi
```
* 启动网站
```
nohup uwsgi --ini uwsgi.ini &
```



# 未来可能收费的功能列表：
* Offie系列产品的在线修改功能；
* 主从盘同步功能；
* 付费查看功能；
* 采集功能；
* 会员等级制度功能；
* 压缩包上传解压同步功能；
* 文件夹上传同步功能；