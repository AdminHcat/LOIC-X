## 关于

低轨道离子炮（**LOIC**）是一个使用C#编写的开源网络压测工具

## 免责声明

LOIC仅用于教育目的，旨在帮助服务器所有者培养“防御黑客”的态度。此工具不保证任何维护。

**您不得将本软件用于非法或不道德的目的。这包括引起刑事或民事责任的活动**

**在任何情况下，许可方均不对被许可方的任何活动或不当行为负责**

## 如何在Windows上运行

- 下载LOIC客户端
- 需要 [`Microsoft .NET Framework 3.5 Service Pack 1`](https://www.microsoft.com/zh-CN/download/details.aspx?id=22) 运行库

## 如何在Linux/MacOS上运行

- 使用Mono或Wine运行调试二进制文件

- 阅读[Wiki](https://github.com/AdminHcat/LOIC-X/wiki/_pages)了解最新说明

## Hivemind/隐藏模式

Hivemind模式将您的LOIC客户端连接到IRC服务器，以便您所运行的LOIC客户端被远程控制。 可以将其视为一个自愿的僵尸网络。请注意，您的LOIC客户端被远程的时候可能会失灵。

注意：它不允许远程管理您的机器；该模式只是提供对LOIC客户端本身的控制。

如果要在Hivemind模式下启动，请运行以下操作：

```
LOIC.exe /hivemind IRC服务器地址
```

这样会连接到 `irc://IRC服务器地址:6667/loic`

您还可以指定一个端口和通道：

```
LOIC.exe /hivemind IRC服务器地址 1234 #secret
```

这样会连接到 `irc://irc.server.adress:1234/secret`

要运行Hivemind隐藏模式，请运行以下操作：

```
LOIC.exe /hidden /hivemind IRC服务器地址
```

这样会连接到 `irc://IRC服务器地址:6667/loic` 并且没有任何窗口。

## IRC如何控制LOIC

设置好IRC服务器频道标题而且**频道标题结尾不能有`start`字样**并发送参数消息（例如：

```
!lazor targetip=127.0.0.1 message=test_test port=80 method=tcp wait=false random=true
```

要发起攻击，请发送：

```
!lazor start
```

或者直接在参数消息末尾加上`start`：

```
!lazor targetip=127.0.0.1 message=test_test port=80 method=tcp wait=false random=true start
```

将所有已连接的LOIC客户端的选项重置为默认值：

```
!lazor default
```

停止攻击：

```
!lazor stop
```

查看源代码以了解更多详细信息