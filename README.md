## 介绍
CSocks 使用Golang编写（其实只是因为这段时间对Golang比较感兴趣）基于socks5协议。功能就是可以配合SwitchyOmega实现科学上网（由于加密简单，速度非常快哦！）。

## 如何使用
1. 首先你需要有一台在墙外的服务器，外加golang的环境（本人较懒，还没做release）。

2. 把Csocks项目克隆到墙外的服务器上。这里需要根据自己的服务器IP地址简单修改一下源代码，编辑/csocks/server/server.go文件第16行换成自己服务器公网的IP地址。

3. 服务器需要执行的命令：

    $cd /csocks/server/

    $go build -ldflags "-s -w" server.go

    $./server &

4. 在克隆一份Csocks到你的本地电脑上。这里需要根据自己的服务器IP地址简单修改一下源代码，编辑/csocks/local/local.go文件第14行remoteAddr换成自己服务器公网的IP地址。

5. 客户端需要执行的命令：
    
    $cd /csocks/local/

    $go build -ldflags "-s -w" local.go

    $./local
6. 最后配置一下SwitchyOmega即可愉快地科学上网了。

## 感谢
最后感谢[lightsocks](https://github.com/gwuhaolin/lightsocks)项目！