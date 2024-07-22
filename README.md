# Traffic Rules for Subscription Conversion and DNS Leak Prevention (Based on ACL4SSR)

Traffic rules for Clash

The traffic rules provided in this project can be used with the following tools:

- Clash
- Clash for Windows
- Clash for Android
- OpenClash

## Features

- **Subscription Conversion**: Converts subscription links into compatible split traffic rules.
- **DNS Leak Prevention**: Ensures that DNS is not leaked during use.

## Usage Guide - General Subscription Conversion

If the website you are using does not provide a subscription for the corresponding software, or if you need to use custom rules, or if you cannot download the subscription even after changing DNS, you may need to convert the subscription link yourself.

## Using SubConverter for Subscription Conversion

**SubConverter** is a powerful subscription conversion tool developed by XTindy, supporting mainstream subscription formats including SIP002, Clash, ShadowsocksR, and more. You can choose to use public online conversion services or set up your own service.

### Using Public Online Conversion Services

1. **Visit an Online Subscription Conversion Website**:
   - Choose a public online subscription conversion website based on your preference.

2. **Basic Settings**:
   - In the subscription link input box, paste your SS/SSR/VMESS/TROJAN subscription link.
   - Select the target format you need to convert to (e.g., Clash).
   - You can choose the default backend address or select another backend address as needed.

3. **Advanced Settings** (Recommended):
   - If your tool supports more complex traffic split settings, go to advanced settings.
   - In advanced settings, you can check the options for Emoji and UDP. This will add flags representing the location to the front of all node names.

4. **Generate Subscription Link**:
   - After selecting the options, click the “Generate Subscription Link” button.
   - Click the copy button next to the generated link to copy the new subscription link and paste it into your proxy tool (such as Clash).

### Important Notes

- **Emoji and UDP Settings**: Enabling the Emoji option will add flags representing the location to node names, and enabling the UDP option ensures better network performance.
- **Selecting the Correct Client**: Ensure that you choose the subscription format that matches your proxy tool, such as Clash, Quantumult X, etc.

## Other Rule Conversions (Clash, Quantumult, Surge, Surfboard, Trojan)

Both the frontend and backend are open-source, and it's easy to set up yourself. If you build your own, just setting up the backend is sufficient.
- **Frontend**: [sub-web](https://github.com/CareyWang/sub-web)
- **Backend**: [subconverter](https://github.com/tindy2013/subconverter/blob/master/README-cn.md)

### Using SubConverter for Self-Hosted Service

1. **Download and Install SubConverter**:
   - You can download and install SubConverter from the [SubConverter GitHub page](https://github.com/tindy2013/subconverter).
   - Refer to the [SubConverter README](https://github.com/tindy2013/subconverter/blob/master/README-cn.md) for configuration details.

2. **Configure SubConverter**:
   - Configure SubConverter’s parameters and options according to your needs.
   - Start SubConverter and perform subscription conversion.

3. **Import Converted Subscription Links**:
   - Paste the converted subscription links into your proxy tool.

By following these steps, you can easily convert subscription links into the required format and use them in your proxy tool.

## Supported Types

| Type                         | Source Type | Target Type | Parameters        |
|------------------------------|:-----------:|:-----------:|-------------------|
| Clash                        |    ✓        |    ✓        | clash             |
| ClashR                       |    ✓        |    ✓        | clashr            |
| Quantumult (Full Config)     |    ✓        |    ✓        | quan              |
| Quantumult X (Full Config)   |    ✓        |    ✓        | quanx             |
| Loon                         |    ✓        |    ✓        | loon              |
| Mellow                       |    ✓        |    ✓        | mellow            |
| SS (SIP002)                  |    ✓        |    ✓        | ss                |
| SS (Software Subscription)   |    ✓        |    ✓        | sssub             |
| SSD                          |    ✓        |    ✓        | ssd               |
| SSR                          |    ✓        |    ✓        | ssr               |
| Surfboard                    |    ✓        |    ✓        | surfboard         |
| Surge 2                      |    ✓        |    ✓        | surge&ver=2       |
| Surge 3                      |    ✓        |    ✓        | surge&ver=3       |
| Surge 4                      |    ✓        |    ✓        | surge&ver=4       |
| Trojan                       |    ✓        |    ✓        | trojan            |
| V2Ray                        |    ✓        |    ✓        | v2ray             |
| TG Proxy HTTP/Socks Links    |    ✓        |    ×        | Only supports &url= |

## Notes

**US Node Group Matching Issue**: Some airport nodes may be named US/AUS/RUS, and nodes containing US will be allocated to the US node group. In this case, replace the original `custom_proxy_group=🇺🇲 US Nodes` line with the following strategy groups:

```yaml
custom_proxy_group=🇺🇲 US Nodes`url-test`([^A-Z]美|Portland|Dallas|Oregon|Phoenix|Fremont|Silicon Valley|Las Vegas|Los Angeles|San Jose|Santa Clara|Seattle|Chicago|[^A-Z]US|United States)`http://www.gstatic.com/generate_204`300,,150
custom_proxy_group=🇦🇺 Australian Nodes`url-test`([^A-Z]AUS|Australia|Sydney|Melbourne|Perth|Brisbane|Adelaide|Canberra|AU|Australia)`http://www.gstatic.com/generate_204`300,,50
custom_proxy_group=🇷🇺 Russian Nodes`url-test`([^A-Z]RUS|Russia|Moscow|St.Petersburg|RU|Russia)`http://www.gstatic.com/generate_204`300,,50
