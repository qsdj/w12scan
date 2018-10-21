# w12scan
网络资产收集系统 :)

## 新的架构
- 针对多IP或多域名，所以一次最好”喂"足够的地址。思路来自 http://live.freebuf.com/detail/4c1b47b5026fee25300ea17040ed6ceb  
- 首先所有域名转换为IP或者IP段，masscan + nmap扫描端口并识别指纹，探测出所有未授权访问的漏洞，ip以及详情入库。将IP中HTTP服务加入到域名列表准备扫描。  
- 子域名接口自动获取子域名并DNS验证。验证成功加入到域名列表。  
- 域名扫描会先请求web端，查看域名是否扫描过。以及顶级域名是否whois查询过。  
- 接着对域名进行简单的文件扫描，目录扫描，获取标题，wappanalysise，CMS识别。这是可扩展插件化的（模仿w9scan插件化）。  
- 扫描程序打包成docker，docker化的"分布式"

## 搜索
1. WEB展示最近入库信息（模仿zoomeye）
2. 搜索URL时，自动关联顶级域名whois和子域名以及扫描结果和子域名对应IP的扫描结果。

## 技术
1. Django RESTFUL
2. 数据库暂时想的是MySQL

## End
just for fun!
