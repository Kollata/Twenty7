# Subscription Conversion Rules and DNS Leak Protection
(Reference from ACL4SSR)

**Flow Rules for Clash**

 [中文文档](https://github.com/Kollata/Twenty7/blob/main/README.md)

The flow rules provided by this project can be used with the following tools:

- Clash
- Clash for Windows
- Clash for Android
- OpenClash

## Features

- **Subscription Conversion**: Convert subscription links to compatible flow rules.
- **DNS Leak Protection**: Ensure DNS is not leaked during use.

## Usage Instructions - General Subscription Conversion Guide

If the website you use does not provide a subscription for the corresponding software, or if you need to use custom rules, or if you still cannot download subscriptions after modifying DNS, you may need to convert the subscription link yourself.

## Using SubConverter for Subscription Conversion

**SubConverter** is a powerful subscription conversion tool developed by XTindy, supporting major subscription formats including SIP002, Clash, and ShadowsocksR. You can choose to use public online conversion services or set up your own service for conversion.

### Using Public Online Conversion Services

1. **Visit an Online Subscription Conversion Website**:
   - Choose a public online subscription conversion website by searching for it yourself.

2. **Basic Settings**:
   - In the subscription link input box, paste your SS/SSR/VMESS/TROJAN subscription link.
   - Select the target format you need (e.g., Clash).
   - You can choose the default backend address or select another backend address as needed.

3. **Advanced Settings** (Recommended):
   - If your tool supports more complex flow settings, enter the advanced settings.
   - In the advanced settings, you can check the Emoji and UDP options. This way, all node names will have the flags of their respective regions.

4. **Generate Subscription Link**:
   - After making selections, click the "Generate Subscription Link" button.
   - Click the copy button next to the generated link to paste the new subscription link into your proxy tool (e.g., Clash).

### Important Notes

- **Emoji and UDP Settings**: Enabling the Emoji option in advanced settings will add flags for the regions in front of node names, and enabling the UDP option can ensure better network performance.
- **Select the Correct Client**: Ensure that you select the subscription format that matches your proxy tool, such as Clash or Quantumult X.

## Other Rule Conversions (Clash, Quantumult, Surge, Surfboard, Trojan)

Both the frontend and backend are open-source and it's easy to set up if you want to build it yourself. For self-hosting, just setting up the backend is sufficient.

- **Frontend**: [sub-web](https://github.com/CareyWang/sub-web)
- **Backend**: [subconverter](https://github.com/tindy2013/subconverter/blob/master/README-cn.md)

### Using SubConverter for Self-Hosting

1. **Download and Install SubConverter**:
   - You can download and install SubConverter from the [SubConverter GitHub page](https://github.com/tindy2013/subconverter).
   - Refer to the [SubConverter README](https://github.com/tindy2013/subconverter/blob/master/README-cn.md) for configuration.

2. **Configure SubConverter**:
   - Configure SubConverter parameters and options according to your needs.
   - Start SubConverter and perform subscription conversion.

3. **Import the Converted Subscription Link**:
   - Paste the converted subscription link into your proxy tool.

By following these steps, you can easily convert subscription links into the required format and use them in your proxy tool.

## Supported Types

| Type                         | Source Type | Target Type | Parameter        |
|------------------------------|:-----------:|:-----------:|------------------|
| Clash                        |      ✓      |      ✓      | clash            |
| ClashR                       |      ✓      |      ✓      | clashr           |
| Quantumult (Full Configuration) |      ✓      |      ✓      | quan             |
| Quantumult X (Full Configuration) |      ✓      |      ✓      | quanx            |
| Loon                         |      ✓      |      ✓      | loon             |
| Mellow                       |      ✓      |      ✓      | mellow           |
| SS (SIP002)                  |      ✓      |      ✓      | ss               |
| SS (Software Subscription)   |      ✓      |      ✓      | sssub            |
| SSD                          |      ✓      |      ✓      | ssd              |
| SSR                          |      ✓      |      ✓      | ssr              |
| Surfboard                    |      ✓      |      ✓      | surfboard        |
| Surge 2                      |      ✓      |      ✓      | surge&ver=2      |
| Surge 3                      |      ✓      |      ✓      | surge&ver=3      |
| Surge 4                      |      ✓      |      ✓      | surge&ver=4      |
| Trojan                       |      ✓      |      ✓      | trojan           |
| V2Ray                        |      ✓      |      ✓      | v2ray            |
| HTTP/Socks Links like TG Proxies |   ✓       |      ×      | Only supports &url= call |

## Notes

**US Node Group Policy Issue**: Some nodes might be named US/AUS/RUS, and nodes containing "US" will be grouped under the US node group. In such cases, delete the original line `custom_proxy_group=🇺🇲 美国节点` and replace it with the following policy groups:

```yaml
custom_proxy_group=🇺🇲 US Nodes`url-test`([^A-Z]美|波特兰|达拉斯|俄勒冈|凤凰城|费利蒙|硅谷|拉斯维加斯|洛杉矶|圣何塞|圣克拉拉|西雅图|芝加哥|[^A-Z]US|United States)`http://www.gstatic.com/generate_204`300,,150
custom_proxy_group=🇦🇺 Australia Nodes`url-test`([^A-Z]AUS|澳大利亚|Sydney|Melbourne|Perth|Brisbane|Adelaide|Canberra|AU|Australia)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇷🇺 Russia Nodes`url-test`([^A-Z]RUS|俄罗斯|Moscow|St.Petersburg|RU|Russia)`http://www.gstatic.com/generate_204`300,,50
```

## License

[![CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey)](https://creativecommons.org/licenses/by-sa/4.0/deed.en)

This project is licensed under the [CC BY-SA 4.0 License](https://creativecommons.org/licenses/by-sa/4.0/deed.en).
