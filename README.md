# 简介

本项目每周四自动生成 GeoIP 文件，包括但不限于 V2Ray dat 格式路由规则文件 `geoip.dat` 和 MaxMind mmdb 格式文件 `Country.mmdb`。


## 与官方版 GeoIP 的区别
国家仅包含cn/jp
- 新增类别（方便有特殊需求的用户使用）：
  - `geoip:cloudflare`（`GEOIP,CLOUDFLARE`）
  - `geoip:cloudfront`（`GEOIP,CLOUDFRONT`）
  - `geoip:facebook`（`GEOIP,FACEBOOK`）
  - `geoip:google`（`GEOIP,GOOGLE`）
  - `geoip:netflix`（`GEOIP,NETFLIX`）
  - `geoip:telegram`（`GEOIP,TELEGRAM`）
  - `geoip:twitter`（`GEOIP,TWITTER`）
  - `geoip:bilibili`（`GEOIP,BILIBILI`）
  - `geoip:apple`（`GEOIP,APPLE`）

## License

[CC-BY-SA-4.0](https://creativecommons.org/licenses/by-sa/4.0/)

This product includes GeoLite2 data created by MaxMind, available from [MaxMind](http://www.maxmind.com).

## 项目 Star 数增长趋势

[![Stargazers over time](https://starchart.cc/Loyalsoldier/geoip.svg)](https://starchart.cc/Loyalsoldier/geoip)
