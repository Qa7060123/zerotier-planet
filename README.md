
# 一分钟自建zerotier-planet

源项目地址：https://github.com/Jonnyan404/zerotier-planet

主要增加了可以更改zerotier服务端口的功能



# 必要条件

- 具有公网ip的服务器
- 安装 docker
- 安装 docker-compose
- 防火墙开放TCP端口 6001/6002/6003 和UDP端口 6003

# 用法

```
git clone https://github.com/wxxsk/zerotier-planet

cd zerotier-planet
# 修改docker-compose.yml文件中的IP为你自己的服务器IP
# 如果需要修改zerotier的服务端口6003，需要把docker-compose.yml和patch.sh中的6003全部替换
docker-compose up -d
# 以下步骤为创建planet和moon
docker cp mkmoonworld-x86_64 ztncui:/tmp
docker cp patch.sh ztncui:/tmp
docker exec -it ztncui bash /tmp/patch.sh
docker restart ztncui
```

然后浏览器访问 `http://ip:6001` 打开web控制台界面。

浏览器访问 `http://ip:6002` 打开planet和moon文件下载页面（亦可在项目根目录的`./ztncui/etc/myfs/`里获取）。


- 用户名：admin
- 密码：admin

# 各客户端配置planet

限于篇幅，请到 <https://www.mrdoc.fun/doc/443/> 查阅


# 关联云服务器(带公网IP)

[【腾讯云】云产品限时秒杀，爆款2核4G云服务器，首年74元](https://curl.qcloud.com/S2Db7PLK)


### 私有 zerotier-planet 的优势:
- 解除官方 25 的设备连接数限制
- 提升手机客户端连接的稳定性

# 同类型项目推荐

https://github.com/xubiaolin/docker-zerotier-planet

# Reference Link

- <https://www.mrdoc.fun/doc/443/>
- <https://github.com/key-networks/ztncui-aio>
