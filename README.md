# 🔥 StratumProxy
![webui.jpg](https://github.com/qingshan2048/img/blob/main/webui.jpg)  

## 编译
1. 请自行安装 Golang （>1.16 && 准备编译所需环境
2. 从GitHub拉取源码并切换到编译目录   

编译Linux版本：
```
go env -w GO111MODULE=on
go env -w CGO_ENABLED=0
go env -w GOARCH=amd64
go env -w GOOS=linux
go build -trimpath -ldflags "-s -w -extldflags '-static'" -gcflags=-trimpath=$GOPATH -asmflags=-trimpath=$GOPATH --tags self_cfg,publish_log
```
编译Windows版本：
```
go env -w GO111MODULE=on
go env -w CGO_ENABLED=0
go env -w GOARCH=amd64
go env -w GOOS=windows
go build -trimpath -ldflags "-s -w -extldflags '-static'" -gcflags=-trimpath=$GOPATH -asmflags=-trimpath=$GOPATH --tags self_cfg,publish_log
```

## Windows 直接下载运行 
https://github.com/ethpoolproxy/stratumproxy/releases

## 🔧 Linux一键安装

```bash
bash <(curl -s -L https://raw.githubusercontent.com/ethpoolproxy/stratumproxy/master/install.sh)
```

---

---
## 🔧 Linux手动安装
```bash
wget https://github.com/ethpoolproxy/stratumproxy/releases/download/v1.3.1/stratumproxy_v1.3.1 -O /usr/bin/stratumproxy
wget https://raw.githubusercontent.com/ethpoolproxy/stratumproxy/stratumproxy.service -O /etc/systemd/system/stratumproxy.service
systemctl daemon-reload
systemctl enable --now stratumproxy
```

### 查看运行情况
```bash
systemctl status stratumproxy
```

## 🔨 更新日志

```bigquery
[Rinako] v1.3.2 - Bug修复 | 稳定性优化
优化程序占用和加固稳定性
优化: 安全写入保证不丢份额
优化: 上游生命周期，解决游离上游导致崩溃
优化: 抽水逻辑，更准能抽到了
修复: 创建矿池参数合法性检测无效
修复: 一些极端情况导致软件崩溃

[Rinako] v1.3.1 - Bug修复 | 程序优化
优化: 固定矿机抽水分数限制到 0.62 缓解抽水不准
优化: 输出逻辑
优化: 上游矿池 30 秒内没下发任务则重连
优化: 登陆上游矿池超时 处理
修复: 一些导致程序崩溃的问题

[Rinako] v1.3.0 | Rinako
优化: 用户体验，更多提示
优化: WebUI 外观改善
功能: WebUI 可添加矿池
功能: 多矿池不同币种兼容
功能: WebUI 可修改配置
修复: 若干 Bug
修复[轻度]: 多个认证包开启多个上游导致游离
修复[严重]: 用户抽水时矿机断开导致软件卡死
重构: 核心代码，优化业务逻辑
```

## 🐛 捐赠支持

```bigquery
如果程序对你有帮助，您可以自愿捐赠：
ETH-ERC20 / Polygon
0xB775f5396eBe589C770069Bfcc421Ca135E9a326
Tron-TRC20
TKJVn8Xrs23zi5wgJptxjw4yL9mDxtuSxf
```

## 关于我们
<a href="https://t.me/StratumProxy">StratumProxy Telegram交流群</a>  
<b>声明：此源码仅供学习交流使用，不对您使用造成的后果负责！</b>  
