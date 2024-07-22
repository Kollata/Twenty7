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

## 使用说明

1. **下载并安装Clash或OpenClash**（具体操作请参阅相应工具的官方网站）。
2. **导入本项目提供的分流规则**。
3. **配置你的订阅链接**。
4. **启动Clash或OpenClash**。

## 其他规则转换 clash Quantumul Surge Surfboard Trojan

 前后端都是开源的，自己随便搭建。自建的话，只自建后端已经足够
- **前端**：[sub-web](https://github.com/CareyWang/sub-web)
- **后端**：[subconverter](https://github.com/tindy2013/subconverter/blob/master/README-cn.md)




## 注意事项

**美国节点分组策略组可能存在US匹配问题**：一些机场节点可能命名为US/AUS/RUS，含US的节点会被全部分配到美国节点。这种情况下，请使用以下策略组：

```yaml
custom_proxy_group=🇺🇲 美国节点`url-test`([^A-Z]美|波特兰|达拉斯|俄勒冈|凤凰城|费利蒙|硅谷|拉斯维加斯|洛杉矶|圣何塞|圣克拉拉|西雅图|芝加哥|[^A-Z]US|United States)`http://www.gstatic.com/generate_204`300,,150
custom_proxy_group=🇦🇺 澳洲节点`url-test`([^A-Z]AUS|澳大利亚|Sydney|Melbourne|Perth|Brisbane|Adelaide|Canberra|AU|Australia)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇷🇺 俄罗斯节点`url-test`([^A-Z]RUS|俄罗斯|Moscow|St.Petersburg|RU|Russia)`http://www.gstatic.com/generate_204`300,,50

