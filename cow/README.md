使用说明
========
详细说明请参考cow的项目主页：https://github.com/cyfdecyf/cow

```
------------------------        -------------------------       -----------------------
|                      |        |                       |       |                     |
|   PC with cow agent  |  ===>  | Server with cow proxy |  ===> | Target web server   |
|                      |        |                       |       |                     |
------------------------        -------------------------       -----------------------
```

* 在国外Server上通过此Dockerfile安装cow proxy，监听端口8388。
* PC上可利用Chrome的SwitchySharp插件代理到本地cow agent监听的端口，如7777。
* 在cow agent上设置proxy的地址及协议，如8388。

cow agent
---------
```
listen = http://127.0.0.1:7777
```

cow proxy
---------
```
listen = cow://aes-128-cfb:password@0.0.0.0:8388

sudo docker.io build -t cow .
sudo docker.io run -p 8388:8388 -d -t cow
```
