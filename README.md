# cloudflare2vless
在cloudflare上通过work部署代码，成为v2ray的服务节点，代码参考
优选地址工具

代理地址的选择问题：
使用正常的：let proxyIP = '103.200.112.108';


详细使用说明请看：

Github：https://github.com/XIU2/CloudflareSpeedTest

可以去这里向我 [反馈问题、提供建议、询问使用方法] ！

===================================

# 如果平均延迟非常低（如 0.xx），则说明 CloudflareST 测速时走了代理，请先关闭代理软件后再测速。
# 如果在路由器上运行，请先关闭路由器内的代理（或将其排除），否则测速结果可能会不准确/无法使用。

# 因为每次测速都是在每个 IP 段中随机 IP，所以每次的测速结果都不可能相同，这是正常的！

# 注意！我发现电脑开机后第一次测速延迟会明显偏高（手动 TCPing 也一样），后续测速都正常
# 因此建议大家开机后第一次正式测速前，先随便测几个 IP（无需等待延迟测速完成，只要进度条动了就可以直接关了）

===================================

# 脚本【cfst_host.bat】的作用是 CloudflareST 测速后获取最快 IP 并替换 Hosts 中的 Cloudflare CDN IP。
# 使用前请先阅读：https://github.com/XIU2/CloudflareSpeedTest/discussions/312#discussioncomment-5161576

===================================

# 脚本【cfst_3proxy.bat】的作用为 CloudflareST 测速后获取最快 IP 并替换 3Proxy 配置文件中的 Cloudflare CDN IP。
# 可以把所有 Cloudflare CDN IP 都重定向至最快 IP，实现一劳永逸的加速所有使用 Cloudflare CDN 的网站（不需要一个个添加域名到 Hosts 了）。
# 使用前请先阅读：https://github.com/XIU2/CloudflareSpeedTest/discussions/71

===================================

ip.txt 为 IPv4 数据文件
ipv6.txt 为 IPv6 数据文件

可以使用 -f xx.txt 参数来指定不同的 IP 数据文件（支持 IPv4 + IPv6 混合测速），如：
CloudflareST.exe -f ipv6.txt

也可以直接通过参数指定要测速的 IP，如：
CloudflareST.exe -ip 1.1.1.1,2606:4700::/32
