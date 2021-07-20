介绍：

本示例包括 naiveproxy、trojan-go 应用。两应用服务端以 caddy 源码加 forwardproxy 插件、caddy-trojan 插件编译而成，基于各自插件代理实现科学上网。其应用如下：

1、naiveproxy（基于forwardproxy插件实现，tls由caddy提供及处理，不需配置。）

2、trojan-go（基于caddy-trojan插件实现，tls由caddy提供及处理，不需配置。）

注意：

1、caddy 不小于 v2.3.0 版才支持 Caddyfile 配置开启 h2c server。

2、使用本人 Releases 中编译好的 caddy 文件，才可同时支持 naiveproxy、trojan-go 等应用。

3、本示例的 naiveproxy 支持 http/3 应用，即 quic 协议传输。

3、Caddyfile 配置与 caddy.json 配置二选一（效果一样）。支持自动 https，即自动申请与更新证书与私钥，自动 http 重定向到 https。

4、此 trojan-go 应用完全兼容 trojan，还有自己的特色：支持 Websocket，可与一般 Trojan 流量共存；支持 CDN 流量中转(基于 WebSocket over TLS)。