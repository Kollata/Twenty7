# 订阅转换用的分流规则，防DNS泄露

用于clash的分流规则

本项目提供的分流规则可用于以下工具：

- Clash
- Clash for Windows
- Clash for Android
- OpenClash

## 功能

- **订阅转换**：将订阅链接转换为兼容的分流规则。
- **防DNS泄露**：确保在使用过程中DNS不会泄露。

## 使用说明-通用订阅转换指南

如果您使用的网站没有提供相应软件的订阅，或需要使用自定义规则，或者在修改 DNS 后仍无法下载订阅，您可能需要自行转换订阅链接。

## 使用 SubConverter 进行订阅转换

**SubConverter** 是一个功能强大的订阅转换工具，由 XTindy 开发，支持包括 SIP002、Clash、ShadowsocksR 等主流订阅格式。您可以选择使用公用的在线转换服务或自建服务进行转换。

### 使用公用在线转换服务

1. **访问在线订阅转换网站**：
   - 选择一个公用的在线订阅转换网站，自行搜索选择。

2. **基础设置**：
   - 在订阅链接输入框中，粘贴您的机场 SS/SSR/VMESS/TROJAN 等订阅链接。
   - 选择您需要转换的目标格式（例如 Clash）。
   - 后端地址可以选择默认设置，或者根据需要选择其他后端地址。

3. **进阶设置**（推荐）：
   - 如果您的工具支持更复杂的分流设置，进入进阶设置。
   - 在进阶设置中，可以勾选 Emoji 和 UDP 选项。这样，所有节点名称前将带有所在地区的旗帜。

4. **生成订阅链接**：
   - 选择完毕后，点击“生成订阅链接”按钮。
   - 单击生成后的链接旁边的复制按钮，将新生成的订阅链接粘贴到您的代理工具（如 Clash）中即可。

### 重要说明

- **Emoji 和 UDP 设置**：在进阶设置中，启用 Emoji 选项会在节点名称前添加所在地区的旗帜，启用 UDP 选项可以确保更好的网络性能。
- **选择正确的客户端**：确保选择与您代理工具匹配的订阅格式，如 Clash、Quantumult X 等。

## 其他规则转换 clash Quantumul Surge Surfboard Trojan

 前后端都是开源的，想自己搭建的话很简单。自建的话，只自建后端已经足够
- **前端**：[sub-web](https://github.com/CareyWang/sub-web)
- **后端**：[subconverter](https://github.com/tindy2013/subconverter/blob/master/README-cn.md)

### 使用 SubConverter 自建服务

1. **下载并安装 SubConverter**：
   - 您可以从 [SubConverter 的 GitHub 页面](https://github.com/tindy2013/subconverter) 下载并安装 SubConverter。
   - 参考 [SubConverter 的 README](https://github.com/tindy2013/subconverter/blob/master/README-cn.md) 进行配置。

2. **配置 SubConverter**：
   - 根据您的需求，配置 SubConverter 的参数和选项。
   - 启动 SubConverter 并进行订阅转换。

3. **导入转换后的订阅链接**：
   - 将转换后的订阅链接粘贴到您的代理工具中。

通过这些步骤，您可以方便地将订阅链接转换为所需的格式，并在代理工具中进行使用。

## 支持类型

| 类型                         | 作为源类型 | 作为目标类型 | 参数            |
|----------------------------|:--------:|:--------:|-----------------|
| Clash                      |    ✓     |    ✓     | clash           |
| ClashR                     |    ✓     |    ✓     | clashr          |
| Quantumult (完整配置)       |    ✓     |    ✓     | quan            |
| Quantumult X (完整配置)     |    ✓     |    ✓     | quanx           |
| Loon                       |    ✓     |    ✓     | loon            |
| Mellow                     |    ✓     |    ✓     | mellow          |
| SS (SIP002)                |    ✓     |    ✓     | ss              |
| SS (软件订阅)               |    ✓     |    ✓     | sssub           |
| SSD                        |    ✓     |    ✓     | ssd             |
| SSR                        |    ✓     |    ✓     | ssr             |
| Surfboard                  |    ✓     |    ✓     | surfboard       |
| Surge 2                    |    ✓     |    ✓     | surge&ver=2     |
| Surge 3                    |    ✓     |    ✓     | surge&ver=3     |
| Surge 4                    |    ✓     |    ✓     | surge&ver=4     |
| Trojan                     |    ✓     |    ✓     | trojan          |
| V2Ray                      |    ✓     |    ✓     | v2ray           |
| 类 TG 代理的 HTTP/Socks 链接 |    ✓     |    ×     | 仅支持 &url= 调用 |



## 注意事项

**美国节点分组策略组可能存在US匹配问题**：一些机场节点可能命名为US/AUS/RUS，含US的节点会被全部分配到美国节点。这种情况下，请使用以下策略组：

```yaml
custom_proxy_group=🇺🇲 美国节点`url-test`([^A-Z]美|波特兰|达拉斯|俄勒冈|凤凰城|费利蒙|硅谷|拉斯维加斯|洛杉矶|圣何塞|圣克拉拉|西雅图|芝加哥|[^A-Z]US|United States)`http://www.gstatic.com/generate_204`300,,150
custom_proxy_group=🇦🇺 澳洲节点`url-test`([^A-Z]AUS|澳大利亚|Sydney|Melbourne|Perth|Brisbane|Adelaide|Canberra|AU|Australia)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇷🇺 俄罗斯节点`url-test`([^A-Z]RUS|俄罗斯|Moscow|St.Petersburg|RU|Russia)`http://www.gstatic.com/generate_204`300,,50

## 注意事项

**美国节点分组策略组可能存在US匹配问题**：一些机场节点可能命名为US/AUS/RUS，含US的节点会被全部分配到美国节点。这种情况下，请使用以下策略组：

```yaml
# 美国节点分组策略组
custom_proxy_group=🇺🇲 美国节点`url-test`([^A-Z]美|波特兰|达拉斯|俄勒冈|凤凰城|费利蒙|硅谷|拉斯维加斯|洛杉矶|圣何塞|圣克拉拉|西雅图|芝加哥|[^A-Z]US|United States)`http://www.gstatic.com/generate_204`300,,150

# 澳洲节点分组策略组
custom_proxy_group=🇦🇺 澳洲节点`url-test`([^A-Z]AUS|澳大利亚|Sydney|Melbourne|Perth|Brisbane|Adelaide|Canberra|AU|Australia)`http://www.gstatic.com/generate_204`300,,50

# 俄罗斯节点分组策略组
custom_proxy_group=🇷🇺 俄罗斯节点`url-test`([^A-Z]RUS|俄罗斯|Moscow|St.Petersburg|RU|Russia)`http://www.gstatic.com/generate_204`300,,50
