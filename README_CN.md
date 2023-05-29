# Docker ChatGPT

<p style="text-align: center;">
  <a href="README.md">ENGLISH</a> | <a href="README_CN.md"  target="_blank">中文文档</a>
</p>

![](./.github/preview.jpg)

使用 Docker 一键部署的本地版本的 ChatGPT，支持访问多种不同的数据源，以及 OpenAI 不支持的模型。


## 当前版本，主要功能

- 隐私数据由你自己掌控，没有任何行为数据上报。
- 客户端响应速度极快，远超原版。
- 支持增加你自己的数据源（模型或接口）。
- 与官方功能和体验保持一致。

## 使用方法，举些例子

你可以在[示例目录](./examples/)中找到一些现成的配置，进行使用。

- [01.搭配 OpenAI API 使用](./examples/01.use-OpenAI-API/)
- [02.搭配 MidJourney 私有 API 使用](./examples/02.use-Private-MidJourney-API/)
- [03.使用 FlagStudio 免费 API 使用](./examples/03.use-FlagStudio-API/)
- [04.启用官方的新版界面](./examples/04.use-Newlook-UI/)
- [05.如何配置自定义的模型选择列表](./examples/05.use-custom-model-list/)
- [06.如何启用插件功能](./examples/06.use-plugin/)

## 界面截图，一睹为快

<img src=".github/screenshots/let-coding.png" width="80%">

<table><tbody>
<tr><td>会话输出图片</td><td>和插件进行交互</td></tr>
<tr><td><img src=".github/screenshots/conversation-with-image.png" width="90%"></td>
<td><img src=".github/screenshots/conversation-with-plugin.png" width="90%"></td>
</tr>
<tr><td>定制模型筛选器</td><td>客户端配置</td></tr>
<tr><td><img src=".github/screenshots/model-switcher.png" width="90%"></td>
<td><img src=".github/screenshots/settings.png" width="90%"></td>
</tr>
</tbody></table>

## 使用入门，一步步来

1. 通过 `git` 或者下载压缩包，得到项目文件。或者直接选择某个[示例目录](./examples/)中的配置文件。 ( 比如: [examples/01.use-OpenAI-API/docker-compose.yml](examples/01.use-OpenAI-API/docker-compose.yml) )

```bash
# 使用 `git clone` 下载最新版本
git clone https://github.com/soulteary/docker-chatgpt.git
# 或者下载压缩包
wget https://github.com/soulteary/docker-chatgpt/archive/refs/heads/main.zip
```

2. 根据你的实际情况，更新配置文件中的部分配置信息。

```yaml
# OpenAI API 需要填写你自己的
OPENAI_API_KEY: "sk-......"
# 如果你的网络无法直接访问 OpenAI，那么你需要配置下面两个参数
# OPENAI_API_PROXY_ENABLE: "on"
# OPENAI_API_PROXY_ADDR: "http://127.0.0.1:1234"
```

3. 使用 Docker 一键启动项目，开始使用/体验。

```bash
# 临时启动，可以使用下面的命令
docker compose up
# 长期运行可以使用下面的命令
docker compose up -d
```

当服务启动之后，浏览器中访问 `http://localhost:8090`，就能够开始玩啦。

## 如何升级，保持最新

**这个客户端项目将会持续跟随官方项目进行更新，以确保功能能够和官方保持一致。**

你可以使用下面的命令，来下载到最新版本的 Docker 镜像，来确保和项目是一致的：

```bash
# x86_64
docker pull soulteary/chatgpt
# Mac M1/M2
docker pull soulteary/docker-chatgpt:arm64
```

**后端项目将持续更新和完善，用来添加各种各样的新的数据源，尤其是 OpenAI 不会支持的，但确是十分有用的。**

你同样可以通过下面的 Docker 命令，来获取最新版本的软件：

```bash
# 获取默认版本，保持最新
docker pull soulteary/sparrow
# 获取具体的某一个版本
docker pull soulteary/sparrow:v0.9.2
```

然后，使用 `docker compose down && docker compose up -d` 重新启动项目，就完成了升级操作。


更高级的用法，以及之前的一些有趣实践，比如：通过它搜索各种垂直网站、使用MidJoruney 画图，可以参考 [Sparrow 项目](https://github.com/soulteary/sparrow)文档中的视频。

欢迎来一起来玩，贡献这个项目，添加不同的数据类型、或功能。

## 程序性能，小巧快速

之所以项目体验好，是因为项目的访问速度非常快，前端技术评分也非常不错。

![](.github/screenshots/perf.png)

除此之外，程序作为服务日常运行，也只需要 10MB 左右的硬盘空间，10MB 左右的内容，1% 左右的 CPU 资源。

## 关于隐私，老话重提

这个项目**不需要连接任何额外的网络**，除了你指定的后端服务之外。

所以，你可以通过你的网络防火墙，云服务器的安全规则策略来禁用除了你的数据源之外的**任何网络**请求，因为这样不会影响这个客户端正常工作。

如果你有隐私顾虑，请使用上面的方式来处理和解决你的顾虑。

## 相关项目

- 后端服务: 兼容 ChatGPT 接口风格的后端服务，开源实现。 [soulteary/sparrow](https://github.com/soulteary/sparrow)

## License

[WTFPL license](./LICENSE)

协议：你爱干嘛干嘛协议 :)
