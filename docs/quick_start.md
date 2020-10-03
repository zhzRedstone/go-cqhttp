#  开始

欢迎来到 go-cqhttp 文档 目前还在咕

# 基础教程
## 下载
从[release](https://github.com/Mrs4s/go-cqhttp/releases)界面下载最新版本的go-cqhttp

- Windows下32位文件为  `go-cqhttp-v*-windows-386.zip`
- Windows下64位文件为 `go-cqhttp-v*-windows-amd64.zip`
- Windows下arm用(如使用高通CPU的笔记本)文件为 `go-cqhttp-v*-windows-arm.zip`
- Linux下32位文件为 `go-cqhttp-v*-linux-386.tar.gz`
- Linux下64位文件为 `go-cqhttp-v*-linux-amd64.tar.gz`
- Linux下arm用(如树莓派)文件为 `go-cqhttp-v*-linux-arm.tar.gz`
- MD5文件为 `*.md5` ，用于校验文件完整性
- 如果没有你所使用的系统版本或者希望自己构建，请移步[进阶指南-如何自己构建](#如何自己构建)

## 解压

- Windows下请使用自己熟悉的解压软件自行解压
- Linux下在命令行中输入 `tar -xzvf [文件名]` 

## 使用

### Windows

#### 标准方法

1.  双击`go-cqhttp.exe`此时将提示
```
[WARNING]: 尝试加载配置文件 config.json 失败: 文件不存在
[INFO]: 默认配置文件已生成,请编辑 config.json 后重启程序.
```
2. 参照[config.md](https://github.com/Mrs4s/go-cqhttp/blob/master/docs/config.md)和你所用到的插件的 `README` 填入参数
3. 再次双击`go-cqhttp.exe`
```
[INFO]: 登录成功 欢迎使用: balabala
```

如出现需要认证的信息，请自行认证设备。

此时，基础配置完成

#### 懒人法

1. [下载包含Windows.bat的zip](https://github.com/fkx4-p/go-cqhttp-lazy/archive/master.zip)
2. 解压
3. 将`Windows.bat`复制/剪切到**go-cqhttp**文件夹
4. 双击运行

效果如下

```
QQ account:
[QQ账号]
QQ password:
[QQ密码]
enable http?(Y/n)
[是否开启http(y/n),默认开启]
enable ws?(Y/n)
[是否开启websocket(y/n),默认开启]
请按任意键继续. . .
```

5. 双击`go-cqhttp.exe`
```
[INFO]: 登录成功 欢迎使用: balabala
```

如出现需要认证的信息，请自行认证设备。

此时，基础配置完成

### Linux

#### 标准方法

1. 打开一个命令行/ssh
2. `cd`到解压目录
3. 输入 `./go-cqhttp`，`Enter`运行 ，此时将提示
```
[WARNING]: 尝试加载配置文件 config.json 失败: 文件不存在
[INFO]: 默认配置文件已生成,请编辑 config.json 后重启程序.
```

4. 参照[config.md](https://github.com/Mrs4s/go-cqhttp/blob/master/docs/config.md)和你所用到的插件的 `README` 填入参数
5. 再次输入 `./go-cqhttp`，`Enter`运行
```
[INFO]: 登录成功 欢迎使用: balabala
```

如出现需要认证的信息，请自行认证设备。

此时，基础配置完成

#### 懒人法

暂时咕咕咕了

## 验证http是否成功配置

此时，如果在本地开启的服务器，可以在浏览器输入`http://127.0.0.1:5700/send_private_msg?user_id=[接收者qq号]&message=[发送的信息]`来发送一条测试信息

如果出现`{"data":{"message_id":balabala},"retcode":0,"status":"ok"}`则证明已经成功配置HTTP

# 进阶指南

## 如何自己构建

1. [下载源码](https://github.com/Mrs4s/go-cqhttp/archive/master.zip)并解压 || 使用`git clone https://github.com/Mrs4s/go-cqhttp.git`来拉取

2. [下载golang binary release](https://golang.google.cn/dl/)并安装或者[自己构建golang](https://golang.google.cn/doc/install/source)

3. 在`cmd`或Linux命令行中，`cd`到目录中

4. 输入`go build -ldflags "-s -w -extldflags '-static'"`，`Enter`运行

*注：可以使用*`go env -w GOPROXY=https://goproxy.cn,direct`*来加速国内依赖安装速度*

*注：此时构建后的文件名为*`main`(Linux)或`main.exe`(Windows)



