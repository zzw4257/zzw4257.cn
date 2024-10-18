---
title: 【微指南】救赎你的网站梦
published: 2024-09-29
description: "你是否希望拥有自己的fancy site？是否想从简洁但缺少个性的blog中跳出，寻找更加适合自己的学术-生活-思想笔记一体化展示平台？是否想在内容外强调自己的名字？是否已经决定搭建自己的网站却仍然在域名，DNS服务器，云服务器等付费需求前犹豫？...假设你有上述疑问，那么我相信，本文应该或多或少能解决你的一些疑问"
image: "./002.jpg"
tags: ["website", "github", "guide", "record"]
category: Guides
draft: true
---
# 【微指南】救赎你的网站梦

## 引子

:::warning

下面标注部分比较随性，较为冗杂，不想看笔者曾经故事的可以跳过。

:::

> 我很早就又拥有一个网站的想法和决心，我先是在初一，利用凡科网制作了自己的第一个网站（是的，并非博客，而是网站），随后在2018年，也就是初二那年仿照某著名日报的爆款文章复刻了一个当时最火的个人博客架构——hexo，并部署了一部分markdown笔记。现在你可以在 [这个网站](https://oldblog.zzw4257.cn/) 访问并查看我的初次尝试。可惜的是一直到今天，成为一个庸俗的三本初八生时，我都没有将这个并没有什么理由的期待延续下去。当然，关于那个实现，很粗糙，但又别具匠心。对于一个没有AI的时代，对一个对web一窍不通，更不用说理解 `node.js`原理的人来说，实际上其背后的意义反而比我今天已有的，基于先进的架构，方便的github action等工作流，以及AI和可能起作用的的web知识而生的网站更加珍贵...
>
> 当然写今天这篇文章的目的并不是为了缅怀什么东西，而是为了从头开始，实践并理解个人网站的一些细节和背景。

本文将从域名，DNS服务器，云服务器，本地服务器，第三方博客/内容服务器，自定义方法，网站安全问题，数据和流量分析与增强，来介绍搭建一个网站过程中需要考虑的种种因素，并尝试在这个过程中改善自身。

假设你已经明确了自己是要做内容网站，应用网站，电商网站还是综合性门户资料网站，你可以跳转至[]

## 域名

域名(domain)，一个非必须但很重要的头衔。失去域名的网站，或者说选取不恰当域名的网站，实际上在被访问的第一刻就不能稳定的吸人眼球。

### 关于域名

我想我们有必要简单说明一下域名的基础内容，希望这能有效厘清一些思路。

:::note[域名定义]

域名是互联网中用于识别和定位特定计算机或网络资源的地址，它是一个人类可读的字符串，通常由字母、数字和符号（如“.”）组成。域名将数字IP地址（如192.168.1.1）转换为易于记忆的名称，使用户能够更方便地访问网站或服务。

:::

#### 顶级域名（TLD）

顶级域名是域名结构中最顶层的部分，如 `.com`、`.org`、`.net`等。顶级域名分为两类：

- **通用顶级域名**（gTLD）：如 `.com`、`.net`、`.org`等。
- **国家代码顶级域名**（ccTLD）：如 `.cn`（中国）、`.us`（美国）、`.uk`（英国）等。

#### 一级域名

一级域名是指直接位于顶级域名之下的域名，如 `example.com`中的 `example`。

#### 二级域名

二级域名是指位于一级域名之下的域名，如 `blog.example.com`中的 `blog`。

### 国内外域名分类

#### 国内域名

- **通用**：`.com.cn`、`.net.cn`、`.org.cn`
- **地区**：`.sh.cn`（上海）、`.gz.cn`（广东）
- **行业**：`.gov.cn`（政府）、`.edu.cn`（教育）

#### 国外域名

- **通用**：`.com`、`.net`、`.org`
- **地区**：`.eu`（欧洲）、`.asia`（亚洲）
- **行业**：`.tech`、`.finance`

### 域名提供商

一些知名的域名提供商包括：

- GoDaddy
- Namecheap
- Alibaba Cloud
- Tencent Cloud
- Amazon Route 53

本域名来自阿里云，整体上阿里云的特点是，纯买域名没有免费增值服务，中国域名为主。好处是较为稳定，定价清晰，可增值服务较多。

关于更加个性化的网站域名的选取，我推荐看[这篇文章](https://www.shopify.com/zh/blog/best-domain-registrars)

## DNS服务器

:::note[DNS服务器定义]

域名系统 ([DNS](https://www.cloudflare.com/learning/dns/what-is-dns/)) 是互联网的电话簿。当用户在网络浏览器中键入[域名](https://www.cloudflare.com/learning/dns/glossary/what-is-a-domain-name/)（例如“google.com”或“nytimes.com”）的时候，DNS 负责为这些站点查找正确的 [IP 地址](https://www.cloudflare.com/learning/dns/glossary/what-is-my-ip-address/)。然后，浏览器使用这些地址与[原服务器](https://www.cloudflare.com/learning/cdn/glossary/origin-server/)或 [CDN 边缘服务器](https://www.cloudflare.com/learning/cdn/glossary/edge-server/)进行通信，以访问网站信息。这一切都要归功于 DNS 服务器：专用于回答 DNS 查询的机器。

:::

### DNS记录配置

#### A记录

用于将域名指向IPv4地址。

**配置示例**：

```
example.com. IN A 192.168.1.1
```

#### AAAA记录

用于将域名指向IPv6地址。

**配置示例**：

```
example.com. IN AAAA 2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

#### CNAME记录

用于将域名指向另一个域名。

**配置示例**：

```
www.example.com. IN CNAME example.com.
```

#### 如何测试DNS记录

使用 `nslookup`或 `dig`命令可以测试DNS记录。

**使用nslookup**：

```bash
nslookup
> set type=A
> example.com
```

**使用dig**：

```bash
dig A example.com
dig AAAA example.com
dig CNAME www.example.com
```

### DNS服务器供应商

一句话

### *HTTPS原理

这里浅谈一下协议

HTTPS（超文本传输安全协议）是在HTTP的基础上通过SSL/TLS协议提供了数据加密、数据完整性验证和身份验证。

**原理**：

1. 客户端请求服务器的证书。
2. 服务器响应并发送证书。
3. 客户端验证证书的有效性。
4. 客户端生成加密密钥并使用服务器的公钥加密发送给服务器。
5. 服务器使用私钥解密得到加密密钥。
6. 服务器与客户端使用加密密钥进行加密通信。

## 命令行工具

当然，让我们深入了解这些网络工具的常用扩展用法。

### 实战演示

```bash
$nslookup cubicy.icu
Server:		223.5.5.5
Address:	223.5.5.5#53

$Non-authoritative answer:
Name:	cubicy.icu
Address: 104.21.31.206
Name:	cubicy.icu
Address: 172.67.179.244

$nslookup -type=NS cubicy.icu
Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
cubicy.icu	nameserver = itzel.ns.cloudflare.com.
cubicy.icu	nameserver = sam.ns.cloudflare.com.

Authoritative answers can be found from:
sam.ns.cloudflare.com	internet address = 108.162.193.141
sam.ns.cloudflare.com	internet address = 172.64.33.141
sam.ns.cloudflare.com	internet address = 173.245.59.141
itzel.ns.cloudflare.com	internet address = 108.162.194.42
itzel.ns.cloudflare.com	internet address = 162.159.38.42
itzel.ns.cloudflare.com	internet address = 172.64.34.42
sam.ns.cloudflare.com	has AAAA address 2606:4700:58::adf5:3b8d
sam.ns.cloudflare.com	has AAAA address 2803:f800:50::6ca2:c18d
sam.ns.cloudflare.com	has AAAA address 2a06:98c1:50::ac40:218d
itzel.ns.cloudflare.com	has AAAA address 2606:4700:50::a29f:262a
itzel.ns.cloudflare.com	has AAAA address 2803:f800:50::6ca2:c22a
itzel.ns.cloudflare.com	has AAAA address 2a06:98c1:50::ac40:222a

$nslookup -type=A cubicy.icu
Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	cubicy.icu
Address: 172.67.179.244
Name:	cubicy.icu
Address: 104.21.31.206

$for i in {1..5}; do nslookup -type=A cubicy.icu; done
Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	cubicy.icu
Address: 104.21.31.206
Name:	cubicy.icu
Address: 172.67.179.244

Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	cubicy.icu
Address: 104.21.31.206
Name:	cubicy.icu
Address: 172.67.179.244

Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	cubicy.icu
Address: 104.21.31.206
Name:	cubicy.icu
Address: 172.67.179.244

Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	cubicy.icu
Address: 172.67.179.244
Name:	cubicy.icu
Address: 104.21.31.206

Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	cubicy.icu
Address: 104.21.31.206
Name:	cubicy.icu
Address: 172.67.179.244

$nslookup -type=TXT cubicy.icu
Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
cubicy.icu	text = "v=spf1 -all"
cubicy.icu	text = "5aSx5oGL44K944Oz44Kw5rKi5bGx6IG044GE44GmCuazo+OBhOOBpuOBsOOBi+OCiuOBruengeOBr+OCguOBhgrmjajjgabjgZ/jgYTjgYvjgokK5b+Y44KM44Gf44GE44GL44KJCuOCguOBhiDlkJvjga7jgZPjgajjgarjgpPjgaYK5b+Y44KM44Gh44KD44GG44GL44KJ44GtICAKU1VLSVNVS0lTVUtJU1VLSVNVS0k="
cubicy.icu	text = "google-site-verification=1fhjV2lfeA6mIocyby2UVcZ8bC8o8NpJreyw1OLPDUY"

Authoritative answers can be found from:

$echo "5aSx5oGL44K944Oz44Kw5rKi5bGx6IG044GE44GmCuazo+OBhOOBpuOBsOOBi+OCiuOBruengeOBr+OCguOBhgrmjajjgabjgZ/jgYTjgYvjgokK5b+Y44KM44Gf44GE44GL44KJCuOCguOBhiDlkJvjga7jgZPjgajjgarjgpPjgaYK5b+Y44KM44Gh44KD44GG44GL44KJ44GtICAKU1VLSVNVS0lTVUtJU1VLSVNVS0k=" | base64 --decode
失恋ソング沢山聴いて
泣いてばかりの私はもう
捨てたいから
忘れたいから
もう 君のことなんて
忘れちゃうからね
SUKISUKISUKISUKISUKI%
$nslookup -type=A www.cubicy.icu
$nslookup -type=A blog.cubicy.icu
Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	www.cubicy.icu
Address: 172.67.179.244
Name:	www.cubicy.icu
Address: 104.21.31.206

Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	blog.cubicy.icu
Address: 104.21.31.206
Name:	blog.cubicy.icu
Address: 172.67.179.244
```

以下是对整个过程的简练总结：

1. **查询权威域名服务器**：

   - 使用命令 `nslookup -type=NS cubicy.icu`，得知权威域名服务器为 Cloudflare 的两个名称服务器。
2. **查询 IP 地址**：

   - 使用命令 `nslookup -type=A cubicy.icu`，返回两个 IP 地址：**172.67.179.244** 和 **104.21.31.206**。
3. **多次查询 A 记录**：

   - 运行循环查询，得到相同的 IP 地址，表明 DNS 记录稳定。
4. **DNS 的好处**：

   - 返回不同 IP 地址有助于负载均衡和故障转移，提高可用性和用户体验。
5. **查找 Base64 编码文本**：

   - 使用命令 `nslookup -type=TXT cubicy.icu`，找到 Base64 编码文本并成功解码为与失恋相关的歌词。
6. **查询子域名的 IP 地址**：

   - 查询 `www.cubicy.icu` 和 `blog.cubicy.icu`，得知它们指向相同的 IP 地址。
7. **直接访问 IP 地址**：

   - 尝试直接访问 IP 地址，结果显示 Cloudflare 阻止了直接访问，要求有效的主机头。
8. **推测使用的服务和技术**：

   - YYY 利用 Cloudflare 提供的 CDN、DNS 解析、DDoS 防护和 IP 地址隐藏等服务。

类似的

本网站的权威DNS服务器是

```bash
zzw4257.cn	nameserver = melnicoff.ns.cloudflare.com.
zzw4257.cn	nameserver = adel.ns.cloudflare.com.
```

IP地址是

```bash
nslookup -type=A zzw4257.cn
Server:		223.5.5.5
Address:	223.5.5.5#53

Non-authoritative answer:
Name:	zzw4257.cn
Address: 172.67.144.224
Name:	zzw4257.cn
Address: 104.21.39.114
```

但是，这引发了另一个矛盾，我的网站实际上是基于githubpages搭建的，为何却能通过nslookup到其A记录呢。实际上是，这是cloudflare的CDN加速功能的"锅"。

### nslookup

`nslookup` 是一个用于查询DNS信息的工具。

**常用用法**：

- 查询指定类型的记录：
  ```bash
  nslookup -type=A example.com
  ```
- 使用特定的DNS服务器进行查询：
  ```bash
  nslookup example.com 8.8.8.8
  ```

**扩展用法**：

- 列出所有类型的DNS记录：
  ```bash
  nslookup -type=any example.com
  ```
- 列出指定域名的反向DNS记录：
  ```bash
  nslookup -type=PTR 8.8.8.8
  ```

### dig

`dig` 是一个用于DNS查询的工具，功能比 `nslookup` 更强大。

**常用用法**：

- 查询A记录：
  ```bash
  dig A example.com
  ```
- 使用特定的DNS服务器：
  ```bash
  dig @8.8.8.8 A example.com
  ```

**扩展用法**：

- 查询并显示详细的查询过程：
  ```bash
  dig +trace example.com
  ```
- 查询MX记录：
  ```bash
  dig MX example.com
  ```
- 查询TXT记录：
  ```bash
  dig TXT example.com
  ```
- 查询NS记录：
  ```bash
  dig NS example.com
  ```
- 使用TCP协议查询：
  ```bash
  dig +tcp A example.com
  ```
- 限制递归查询：
  ```bash
  dig +norecurse A example.com
  ```
- 只显示查询结果：
  ```bash
  dig +short A example.com
  ```

### curl

`curl` 是一个用于传输数据的工具，常用于测试HTTP请求。

**常用用法**：

- 发送GET请求：
  ```bash
  curl example.com
  ```
- 发送HEAD请求：
  ```bash
  curl -I example.com
  ```

**扩展用法**：

- 发送POST请求：
  ```bash
  curl -d "param=value" example.com
  ```
- 发送PUT请求：
  ```bash
  curl -X PUT -d "param=value" example.com
  ```
- 上传文件：
  ```bash
  curl -F "file=@localfile.txt" example.com
  ```
- 使用HTTPS：
  ```bash
  curl -k https://example.com
  ```
- 包含请求头：
  ```bash
  curl -H "X-My-Header: 123" example.com
  ```
- 保存响应到文件：
  ```bash
  curl -o filename example.com
  ```
- 使用代理：
  ```bash
  curl -x http://proxyserver:port example.com
  ```
- 显示详细过程：
  ```bash
  curl -v example.com
  ```

### host

`host` 是一个用于查询DNS信息的工具。

**常用用法**：

- 查询A记录：
  ```bash
  host example.com
  ```
- 查询MX记录：
  ```bash
  host -t MX example.com
  ```

**扩展用法**：

- 查询NS记录：
  ```bash
  host -t NS example.com
  ```
- 查询PTR记录：
  ```bash
  host -t PTR example.com
  ```
- 使用指定DNS服务器：
  ```bash
  host example.com ns.example.com
  ```

### traceroute

`traceroute` 是一个用于显示数据包到达目标主机所经过的路由的工具。

**常用用法**：

- 追踪到目标主机的路由：
  ```bash
  traceroute example.com
  ```

**扩展用法**：

- 使用IPv6：
  ```bash
  traceroute -6 example.com
  ```
- 设置最大跳数：
  ```bash
  traceroute -m 10 example.com
  ```
- 使用ICMP协议：
  ```bash
  traceroute -I example.com
  ```
- 使用UDP协议：
  ```bash
  traceroute -P 33000 example.com
  ```

### ping

`ping` 是一个用于测试网络连接质量的工具。

**常用用法**：

- 测试网络连接：
  ```bash
  ping example.com
  ```

**扩展用法**：

- 设置超时时间：
  ```bash
  ping -W 5 example.com
  ```
- 设置数据包大小：
  ```bash
  ping -s 1500 example.com
  ```
- 指定发送次数：
  ```bash
  ping -c 4 example.com
  ```
- 使用IPv6：
  ```bash
  ping -6 example.com
  ```

这些工具和参数可以帮助你进行网络诊断和测试。如果你需要更多信息或者有其他问题，请随时告诉我。

## DNS服务器和云服务器

## 第三方内容服务器【假设需要】

### github pages【一个不好也不坏的入门选择】

### Wordpress【传统但不失时髦的选择】

## 数据分析

### google analytics

### cloudflare为代表免费分析器

## 网站安全
