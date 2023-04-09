# 简介

本项目每周四自动生成 GeoIP 文件，同时提供命令行界面（CLI）供用户自行定制 GeoIP 文件，包括但不限于 V2Ray dat 格式路由规则文件 `geoip.dat` 和 MaxMind mmdb 格式文件 `Country.mmdb`。

This project releases GeoIP files automatically every Thursday. It also provides a command line interface(CLI) for users to customize their own GeoIP files, included but not limited to V2Ray dat format file `geoip.dat` and MaxMind mmdb format file `Country.mmdb`.

## 与官方版 GeoIP 的区别
国家仅包含cn
- 新增类别（方便有特殊需求的用户使用）：
  - `geoip:cloudflare`（`GEOIP,CLOUDFLARE`）
  - `geoip:cloudfront`（`GEOIP,CLOUDFRONT`）
  - `geoip:facebook`（`GEOIP,FACEBOOK`）
  - `geoip:google`（`GEOIP,GOOGLE`）
  - `geoip:netflix`（`GEOIP,NETFLIX`）
  - `geoip:telegram`（`GEOIP,TELEGRAM`）
  - `geoip:twitter`（`GEOIP,TWITTER`）

## 参考配置

在 [V2Ray](https://github.com/v2fly/v2ray-core) 中使用本项目 `.dat` 格式文件的参考配置：

```json
"routing": {
  "rules": [
    {
      "type": "field",
      "outboundTag": "Direct",
      "ip": [
        "geoip:cn",
        "geoip:private",
        "ext:cn.dat:cn",
        "ext:private.dat:private",
        "ext:geoip-only-cn-private.dat:cn",
        "ext:geoip-only-cn-private.dat:private"
      ]
    },
    {
      "type": "field",
      "outboundTag": "Proxy",
      "ip": [
        "geoip:us",
        "geoip:jp",
        "geoip:facebook",
        "geoip:telegram",
        "ext:geoip-asn.dat:facebook",
        "ext:geoip-asn.dat:telegram"
      ]
    }
  ]
}
```

在 [Clash](https://github.com/Dreamacro/clash) 中使用本项目 `.mmdb` 格式文件的参考配置：

```yaml
rules:
  - GEOIP,PRIVATE,policy,no-resolve
  - GEOIP,FACEBOOK,policy
  - GEOIP,CN,policy,no-resolve
```

在 [Leaf](https://github.com/eycorsican/leaf) 中使用本项目 `.mmdb` 格式文件的参考配置，查看[官方 README](https://github.com/eycorsican/leaf/blob/master/README.zh.md#geoip)。

## 下载地址

> 如果无法访问域名 `raw.githubusercontent.com`，可以使用第二个地址 `cdn.jsdelivr.net`。
> *.sha256sum 为校验文件。

### V2Ray dat 格式路由规则文件

> 适用于 [V2Ray](https://github.com/v2fly/v2ray-core)、[Xray-core](https://github.com/XTLS/Xray-core) 和 [Trojan-Go](https://github.com/p4gefau1t/trojan-go)。

- **geoip.dat**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip.dat](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip.dat)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip.dat](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip.dat)
- **geoip.dat.sha256sum**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip.dat.sha256sum](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip.dat.sha256sum)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip.dat.sha256sum](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip.dat.sha256sum)
- **geoip-only-cn-private.dat**（精简版 GeoIP，只包含 `geoip:cn` 和 `geoip:private`）：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip-only-cn-private.dat](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip-only-cn-private.dat)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip-only-cn-private.dat](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip-only-cn-private.dat)
- **geoip-only-cn-private.dat.sha256sum**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip-only-cn-private.dat.sha256sum](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip-only-cn-private.dat.sha256sum)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip-only-cn-private.dat.sha256sum](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip-only-cn-private.dat.sha256sum)
- **geoip-asn.dat**（精简版 GeoIP，只包含上述新增类别）：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip-asn.dat](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip-asn.dat)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip-asn.dat](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip-asn.dat)
- **geoip-asn.dat.sha256sum**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip-asn.dat.sha256sum](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/geoip-asn.dat.sha256sum)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip-asn.dat.sha256sum](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/geoip-asn.dat.sha256sum)
- **cn.dat**（精简版 GeoIP，只包含 `geoip:cn`）：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/cn.dat](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/cn.dat)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/cn.dat](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/cn.dat)
- **cn.dat.sha256sum**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/cn.dat.sha256sum](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/cn.dat.sha256sum)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/cn.dat.sha256sum](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/cn.dat.sha256sum)
- **private.dat**（精简版 GeoIP，只包含 `geoip:private`）：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/private.dat](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/private.dat)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/private.dat](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/private.dat)
- **private.dat.sha256sum**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/private.dat.sha256sum](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/private.dat.sha256sum)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/private.dat.sha256sum](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/private.dat.sha256sum)

### MaxMind mmdb 格式文件

> 适用于 [Clash](https://github.com/Dreamacro/clash) 和 [Leaf](https://github.com/eycorsican/leaf)。

- **Country.mmdb**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country.mmdb](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country.mmdb)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country.mmdb](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country.mmdb)
- **Country.mmdb.sha256sum**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country.mmdb.sha256sum](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country.mmdb.sha256sum)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country.mmdb.sha256sum](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country.mmdb.sha256sum)
- **Country-only-cn-private.mmdb**（精简版 GeoIP，只包含 `GEOIP,CN` 和 `GEOIP,PRIVATE`）：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country-only-cn-private.mmdb](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country-only-cn-private.mmdb)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country-only-cn-private.mmdb](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country-only-cn-private.mmdb)
- **Country-only-cn-private.mmdb.sha256sum**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country-only-cn-private.mmdb.sha256sum](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country-only-cn-private.mmdb.sha256sum)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country-only-cn-private.mmdb.sha256sum](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country-only-cn-private.mmdb.sha256sum)
- **Country-asn.mmdb**（精简版 GeoIP，只包含上述新增类别）：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country-asn.mmdb](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country-asn.mmdb)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country-asn.mmdb](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country-asn.mmdb)
- **Country-asn.mmdb.sha256sum**：
  - [https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country-asn.mmdb.sha256sum](https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country-asn.mmdb.sha256sum)
  - [https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country-asn.mmdb.sha256sum](https://cdn.jsdelivr.net/gh/Loyalsoldier/geoip@release/Country-asn.mmdb.sha256sum)


```

## License

[CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/)

This product includes GeoLite2 data created by MaxMind, available from [MaxMind](http://www.maxmind.com).
