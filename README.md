# mkcloud专线VPS怎么选：广港、沪日、沪美、深港IX全套餐价格对比与避坑指南（附真实有效优惠码）

搜 mkcloud 的人，多半是在两个场景里：要么是跨境店铺、直播团队被公网线路的晚高峰折腾够了，听说这家“合规跨境电商专线”延迟低、IP 独享，想确认靠不靠谱、值不值；要么已经决定买，但打开官网看到 IEPL、IPLC、IX、上云互联一堆名词，加上几十个套餐档位，不知道从哪下手。

这篇文章把两件事一次讲完：mkcloud 到底卖的是什么、怎么运作，以及官网目前在售的全部套餐、价格和优惠码现状——所有价格都来自官方产品页和官方知识库的当前口径，而不是测评文里的历史截图。想直接看价格，👉 [查看MKCloud全套餐实时价格与库存](https://bit.ly/MKCLoud)。

**mkcloud 是什么：先把“专线VPS”四个字说清楚**

mkcloud（官网域名 mkcloud.net）是一家主做跨境专线服务器的国人商家，商家自述 2023 年 11 月成立，运营主体为 MKADMD。它交付的不是机场订阅，也不是普通 VPS，而是带专线路径的云服务器/独立服务器：每台机器配 1 个独立入口 IP 和 1 个独立出口 IP，你 SSH 或远程桌面连入口，在机器里跑业务程序，流量自动从出口 IP 走专线路径向外访问。

几个关键机制直接决定它适不适合你：

- **实名与白名单**：全线产品需要中国身份信息实名（手机号+姓名+身份证一致性验证），直连款开通时绑定一个“可连入省份”，只有该省 IP 能连入，省份可以自行切换。官方说明这是为防机场、回国等违规用途。
- **出口只出不进**：出口 IP 不接受公网主动连入，不能拿来公开建站、挂支付回调、收邮件或做游戏服务端。
- **流量双向计费**：计量型套餐按上行+下行双向统计，超量后暂停，可购买流量重置或工单升级；共享带宽是峰值，不保证持续跑满。
- **支付与交付**：支持支付宝，月付/季付/半年付/年付/两年付/三年付可选，现货套餐官方口径约 1 分钟自动开通。

产品线按方向分成四组：香港（广港 IEPL、深港/沪港 IX、厦港/泉港高防）、日本（沪日 IPLC、沪日 IX）、美国（沪美 IPLC、沪美 IX），外加一个不出海的国内优化产品上海 CN2。早期还上过香港—法国方向的独享 IPLC，现在商店已不单独展示这个方向。每条线的“端内延迟”是官方产品资料给的参考值：广港、深港 IX、厦港、泉港 1~2ms，沪港 21ms，沪日 25~28ms，沪美 124~134ms。注意这是专线两端之间的延迟，不含你本地到入口、出口到目标网站的那两段。

**mkcloud 全线路总览：直连三条线 + 一条云厂 IX**

| 线路 | 类型 | 端内延迟（官方参考） | 入口 | 出口 | 接入条件 |
| --- | --- | --- | --- | --- | --- |
| 广港专线 | IEPL | 1~2ms | 腾讯广州八线BGP/广东电信/移动/联通/三线 | 香港BGP | 本地宽带直连，绑一个省 |
| 沪港专线 | IPLC | 21ms | 上海电信 / 上海BGP | 香港BGP | 本地宽带直连，绑一个省 |
| 沪日专线 | IPLC | 25~28ms | 上海电信 / 上海BGP | 日本BGP | 本地宽带直连，绑一个省 |
| 沪美专线 | IPLC | 124~134ms | 上海电信 / 上海BGP | 美国BGP | 本地宽带直连，绑一个省 |
| 深港/沪港/沪日/沪美 IX | 上云互联（IXP） | 对应方向同上 | 云厂优化网络通道 | 香港/日本/美国BGP | 必须有支持的云厂机器做前置 |
| 福港高防（厦港/泉港） | 高防 IPLC | 1~2ms | 厦门BGP / 泉州电信 | 香港BGP | 独享款，本地直连 |
| 上海CN2 | 国内优化 | — | 上海动态联通 | 上海电信CN2 | 白名单或前置模式二选一 |

IX 这条产品线是 mkcloud 的特色，官方称自己是第一家把 IXP 专线做成标品的商家。它的入口没有公网路由，只能从阿里云、腾讯云、百度云国内全网及火山云、华为云对应大区的云厂内网接入，所以你必须先有一台支持范围内的云服务器做前置——这意味着 IX 的报价要加上前置机的钱。换来的好处是不限连入省份、入口不暴露公网。反过来说，如果你没有云厂机器，就不该先买 IX 再“想着应该能连”。

**全套餐价格表（一）：流量计费 · 共享带宽 · 直连线路**

以下均为官方产品页当前展示的月付价，所有套餐标配独享 IPv4 ×2（进+出）、双向流量计费，下单页可切季付/半年付/年付等周期。

广港 IEPL（入口：腾讯广州八线BGP，电信/移动/联通/三线入口可在同页切换；出口香港BGP）：

| 套餐 | CPU/内存/硬盘 | 峰值带宽 | 月流量 | 月付价格（支持季付/年付） | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 500GB＊ | 1核2G/20GB | 150M | 500GB | ¥228 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 1TB | 1核2G/20GB | 200M | 1TB | ¥358 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 2TB | 2核4G/40GB | 300M | 2TB | ¥568 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 4TB | 2核4G/40GB | 300M | 4TB | ¥998 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 6TB | 4核8G/60GB | 500M | 6TB | ¥1388 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 10TB | 4核8G/60GB | 500M | 10TB | ¥2288 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |
| 20TB | 4核8G/60GB | 1G | 20TB | ¥4500 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-sh) |

沪日 IPLC（入口上海电信，另有上海BGP入口变体；出口日本BGP）：

| 套餐 | CPU/内存/硬盘 | 峰值带宽 | 月流量 | 月付价格（支持季付/年付） | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 500GB＊ | 1核2G/20GB | 150M | 500GB | ¥228 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 1TB | 1核2G/20GB | 200M | 1TB | ¥358 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 2TB | 2核4G/40GB | 300M | 2TB | ¥568 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 4TB | 2核4G/40GB | 300M | 4TB | ¥998 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 6TB | 4核8G/60GB | 500M | 6TB | ¥1388 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 10TB | 4核8G/60GB | 500M | 10TB | ¥2288 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |
| 20TB | 4核8G/60GB | 1G | 20TB | ¥4500 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-sh) |

沪港 IPLC（入口上海电信；出口香港BGP，端内 21ms）：

| 套餐 | CPU/内存/硬盘 | 峰值带宽 | 月流量 | 月付价格（支持季付/年付） | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 1TB | 1核2G/20GB | 200M | 1TB | ¥288 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 2TB | 2核4G/40GB | 300M | 2TB | ¥428 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 4TB | 2核4G/40GB | 300M | 4TB | ¥696 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 6TB | 4核8G/60GB | 500M | 6TB | ¥988 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 10TB | 4核8G/60GB | 500M | 10TB | ¥1536 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |
| 20TB | 4核8G/60GB | 1G | 20TB | ¥3072 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-sh) |

沪美 IPLC（入口上海电信；出口美国BGP）：

| 套餐 | CPU/内存/硬盘 | 峰值带宽 | 月流量 | 月付价格（支持季付/年付） | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 1TB | 1核2G/20GB | 200M | 1TB | ¥428 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 2TB | 2核4G/40GB | 300M | 2TB | ¥698 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 4TB | 2核4G/40GB | 300M | 4TB | ¥1258 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 6TB | 4核8G/60GB | 500M | 6TB | ¥1758 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 10TB | 4核8G/60GB | 500M | 10TB | ¥2888 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |
| 20TB | 4核8G/60GB | 1G | 20TB | ¥5666 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-us-sh) |

＊两个入门档说明：广港/沪日的 500GB（¥228）档是官方知识库和多家第三方测评页收录的入门价，目前购物车页有时从 1TB 档起展示；沪美早年还有 100GB（¥198）、500GB（¥258）小档，当前页面默认从 1TB 起显示。小档位是否可售，👉 [进店确认这条线的小档位是否可售](https://bit.ly/MKCLoud)。

**全套餐价格表（二）：独享带宽 · 直连线路**

独享带宽产品的计费逻辑完全不同：按带宽大小收钱，流量不限，适合 24 小时持续跑速率的任务。

广港 IEPL 独享（入口腾讯广州八线BGP，出口香港BGP）：

| 档位 | CPU/内存 | 独享带宽 | 流量 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 5M | 2核4G | 5Mbps | 不限 | ¥500 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |
| 10M | 2核4G | 10Mbps | 不限 | ¥700 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |
| 20M | 2核4G | 20Mbps | 不限 | ¥1320 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |
| 50M | 4核8G | 50Mbps | 不限 | ¥3150 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |
| 100M | 4核8G | 100Mbps | 不限 | ¥5800 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |
| 200M | 4核8G | 200Mbps | 不限 | ¥11600 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |
| 300M | 4核8G | 300Mbps | 不限 | ¥17400 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fgz-hk-ex) |

广东方向另有“大带宽独享专线”（广东三线/移动/联通/电信入口，官方知识库口径 200M–2000M 独享、含 300Gbps DDoS 高防，200M 档参考价 3900 元/月起）；部分单线入口的大档位做到 1G/2G/5G，价格从约 2.2 万到 10.5 万元/月，量大可议价，以产品页实价为准。

沪日 IPLC 独享（入口上海电信，出口日本BGP）：

| 档位 | CPU/内存 | 独享带宽 | 流量 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 5M | 2核4G | 5Mbps | 不限 | ¥600 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-ex) |
| 10M | 2核4G | 10Mbps | 不限 | ¥800 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-ex) |
| 20M | 2核4G | 20Mbps | 不限 | ¥1560 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-ex) |
| 50M | 4核8G | 50Mbps | 不限 | ¥3500 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-ex) |
| 100M | 4核8G | 100Mbps | 不限 | ¥6000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-ex) |
| 200M | 4核8G | 200Mbps | 不限 | ¥12000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-ex) |
| 300M | 4核8G | 300Mbps | 不限 | ¥18000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-jp-ex) |

沪日另有上海BGP入口的独享变体，官方通知群列过 10M 1000 元、20M 1960 元、50M 4500 元、100M 8500 元的口径，与电信入口版本价格不同，下单时注意区分入口。

沪港 IPLC 独享（入口UCloud上海BGP，出口香港BGP）：

| 档位 | CPU/内存 | 独享带宽 | 流量 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 5M | 2核4G | 5Mbps | 不限 | ¥650 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |
| 10M | 2核4G | 10Mbps | 不限 | ¥950 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |
| 20M | 2核4G | 20Mbps | 不限 | ¥1760 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |
| 50M | 4核8G | 50Mbps | 不限 | ¥4000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |
| 100M | 4核8G | 100Mbps | 不限 | ¥7500 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-hk-ex) |

上海电信入口的沪港独享入门价更低：官方知识库口径 5Mbps、不限流量、月付 388 元，两种入口在同页切换。

沪美 IPLC 独享（入口UCloud上海BGP，出口美国BGP）：

| 档位 | CPU/内存 | 独享带宽 | 流量 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 5M | 2核4G | 5Mbps | 不限 | ¥850 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |
| 10M | 2核4G | 10Mbps | 不限 | ¥1300 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |
| 20M | 2核4G | 20Mbps | 不限 | ¥2560 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |
| 50M | 4核8G | 50Mbps | 不限 | ¥6000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |
| 100M | 4核8G | 100Mbps | 不限 | ¥11500 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fshh-us-ex) |

**全套餐价格表（三）：上云互联 IX 与高防、CN2**

IX 共享带宽套餐（入口云厂优化网络通道，超量停机，需自备云厂前置机）。

深港/广港 IX（香港出口，端内 1~2ms；商店里挂在“广东-香港IEPL”下的“上云互联优化入口(IXP)”节点，知识库里也叫深港IX，是同一个产品）：

| 套餐 | CPU/内存/硬盘 | 峰值带宽 | 月流量 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 2TB | 2核4G/40GB | 1G | 2TB | ¥158 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 4TB | 2核4G/40GB | 1G | 4TB | ¥258 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 6TB | 4核8G/40GB | 2G | 6TB | ¥378 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 10TB | 4核8G/40GB | 2G | 10TB | ¥826 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 20TB | 4核8G/40GB | 2G | 20TB | ¥1639 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 30TB | 4核8G/60GB | 3G | 30TB | ¥2458 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 50TB | 8核8G/60GB | 3G | 50TB | ¥3588 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 100TB | 8核16G/80GB | 5G | 100TB | ¥7168 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 200TB | 8核16G/80GB | 5G | 200TB | ¥12288 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |
| 300TB | 8核16G/80GB | 5G | 300TB | ¥18428 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-sh) |

沪港 IX（香港出口，端内 21ms）：

| 套餐 | CPU/内存/硬盘 | 峰值带宽 | 月流量 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 2TB | 2核4G/40GB | 500M | 2TB | ¥198 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 3TB | 2核4G/40GB | 500M | 3TB | ¥288 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 6TB | 4核8G/40GB | 1G | 6TB | ¥398 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 10TB | 4核8G/40GB | 1G | 10TB | ¥666 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 20TB | 4核8G/40GB | 1G | 20TB | ¥1290 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 30TB | 4核8G/60GB | 2G | 30TB | ¥1900 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |
| 50TB | 8核8G/60GB | 2G | 50TB | ¥3120 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh) |

沪日 IX（日本出口，端内 25~28ms；1TB 年付版预售时折合约 99 元/月，预售结束后现价如下）：

| 套餐 | CPU/内存/硬盘 | 峰值带宽 | 月流量 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- | --- |
| 1TB | 2核4G/40GB | 200M | 1TB | ¥166 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 2TB | 2核4G/40GB | 300M | 2TB | ¥268 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 3TB | 2核4G/40GB | 500M | 3TB | ¥358 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 6TB | 4核8G/40GB | 1G | 6TB | ¥688 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 10TB | 4核8G/40GB | 1G | 10TB | ¥1125 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 20TB | 4核8G/40GB | 1G | 20TB | ¥2150 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 30TB | 4核8G/60GB | 2G | 30TB | ¥3165 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |
| 50TB | 8核8G/60GB | 2G | 50TB | ¥5222 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-sh) |

沪美 IX（美国出口）：共享与独享档位均有，目前价格档位以 👉 [查看沪美IX现价与可选档位](https://bit.ly/MKCLoud) 的产品页实况为准。

IX 独享带宽（同样需要云厂前置，流量不限）：

深港/广港 IX 独享（香港出口，1~2ms）：

| 档位 | CPU/内存 | 独享带宽 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- |
| 100M | 2核4G | 100Mbps | ¥1600 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-ex) |
| 200M | 2核4G | 200Mbps | ¥3000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-ex) |
| 500M | 8核8G | 500Mbps | ¥6000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-ex) |
| 1G | 28核64G/512GB | 1Gbps | ¥9000（赠独立服务器） | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-ex) |
| 2G | 28核64G/512GB | 2Gbps | ¥16000（赠独立服务器） | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-ex) |
| 5G | 28核64G/512GB | 5Gbps | ¥35000（赠独立服务器） | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-hk-ex) |

沪日 IX 独享（日本出口）：

| 档位 | CPU/内存 | 独享带宽 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- |
| 20M | 2核4G | 20Mbps | ¥1000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-ex) |
| 50M | 2核4G | 50Mbps | ¥2250 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-ex) |
| 100M | 2核4G | 100Mbps | ¥3700 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-ex) |
| 200M | 2核4G | 200Mbps | ¥7000 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-ex) |
| 500M | 8核8G | 500Mbps | ¥17500 | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-ex) |
| 1G | 28核64G/512GB | 1Gbps | ¥35000（赠独立服务器） | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-ex) |
| 2G | 28核64G/512GB | 2Gbps | ¥70000（赠独立服务器） | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-ex) |
| 5G | 28核64G/512GB | 5Gbps | ¥175000（赠独立服务器） | [ 查看档位](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-jp-ex) |

沪港 IX 也有独享档位，下单页切换“带宽计费(独享带宽)”即可看到，👉 [查看沪港IX套餐现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fcloud-sh-hk-sh)。

福港高防独享（厦港：厦门BGP入口→香港BGP出口，1~2ms）：

| 档位 | CPU/内存 | 独享带宽 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- |
| 200M | 4核8G/40GB | 200Mbps | ¥6000 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fxm-hk-ex) |
| 500M | 8核8G/60GB | 500Mbps | ¥13500 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fxm-hk-ex) |
| 1G | 28核64G/512GB | 1Gbps | ¥24000 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fxm-hk-ex) |
| 2G | 28核64G/512GB | 2Gbps | ¥46000 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fxm-hk-ex) |
| 5G | 28核64G/512GB | 5Gbps | ¥110000 | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fxm-hk-ex) |

泉港（泉州电信入口）是同系列的高防独享款，第三方测评收录其 200M 独享起步约 4200 元/月，比厦港便宜，档位和现价以产品页为准。高防款的防护阈值、清洗范围官方没有完全公开，买之前建议工单确认。

上海 CN2（国内优化，不出海）：

| 配置 | 带宽 | 入口/出口 | 月付价格 | 购买链接 |
| --- | --- | --- | --- | --- |
| 8核16G/60GB | 500M独享，不限流量 | 上海动态联通入口→上海电信CN2出口，活动期另赠上海9929出口，独享IPv4×3 | ¥4500（下单后7天内交付） | [ 查看现价](https://www.mkcloud.net/aff.php?aff=390&url=https%3A%2F%2Fwww.mkcloud.net%2Findex.php%2Fstore%2Fsh-cn2-ex) |

这是稀缺资源型产品，定位是国内访问优化，不是海外出口，别把它当美国或香港节点用。

**优惠码与年付优惠：哪些还能用，哪些别想了**

mkcloud 的促销节奏很快，几乎每个节日都上一轮活动码，而且官方会在活动结束后把旧码明确标注“已失效”。按官方知识库和通知群的口径梳理：

- **MK-8.8（流量计费全场，循环88折）**：这是出现频率最高的码，双旦、618、六一端午、新春等多轮活动都反复出现，第三方优惠码汇总页也长期按“循环88折”收录。它属于“活动码”，官方口径是活动期内有效，但历史活动里反复续期——下单时先试它。
- **MK-7.8（独享带宽全场，首月78折）**：只打首月，第二个月恢复原价。适合先买一个月独享试质量。
- **MK-IEPL-WELCOME / MK-IPLC-WELCOME（专线9折循环）**：来自官方通知群的历史活动口径，时效不确定，可用性以结算页提示为准。
- **已确认结束的码**：MK-NEW（新客活动机 236 元/月）、CLOUD-2T-NEW（2TB 8折）、IXCLOUD（沪日IX预售6.9折）、US-6.9、JP-7.7、MK-8.9、ALIYUN/ALIYUN-NEW——这些都随对应活动关闭失效了，看到旧文章还在推这些码，直接略过。

三个使用要点：优惠码之间不叠加，选最划算的一个填；年付周期通常有额外折扣，第三方测评称约合85折，具体以结算页实价为准；码失效不代表没有别的优惠，官方会不定期直接在后台挂券。与其猜，不如👉 [进店核对当前可用优惠码](https://bit.ly/MKCLoud)，把购物车走到最后一步看系统提示。

**按业务场景选套餐：六种情况的直接答案**

- **华南或全国方向做香港业务（亚马逊、Shopee、TikTok 运营）**：首选广港 IEPL 共享，500GB（¥228）或 1TB（¥358）起步，1~2ms 端内延迟是全产品线最好的数字，香港出口通用性也最强。
- **直播推流、大流量上传**：广港 6TB/10TB（500M 峰值）或 20TB（1G 峰值，¥4500）。如果对持续速率有硬要求（比如长时间推流不能掉），对比独享款，50M 独享 ¥3150 起。
- **已经有阿里云/腾讯云等云厂机器**：直接上 IX 系列，这是全店性价比最高的一档。深港/广港IX 2TB 只要 ¥158 还给 1G 峰值带宽，沪日IX 1TB ¥166。但要算上前置机成本，而且下单页会标明支持的云厂和地域范围。
- **日本市场**：沪日 IPLC 或沪日 IX，25~28ms 端内延迟，日区后台和客户端测试都够用。
- **美国市场**：沪美 IPLC 1TB（¥428）起步，124~134ms 是跨太平洋的物理水平，不用指望更低；流量需求小的话可以问问 100GB/500GB 小档是否可售。
- **金融对港、易被攻击的业务**：沪港 IPLC 独享（21ms 独享隔离，官方选型文里点名适合零容忍抖动的交易场景）或厦港/泉港高防独享。需要 SLA 或路由定制的话，官方明确说默认无 SLA，要提前工单谈。

还有一条反向建议：如果业务必须通过公网 IP 接收外部请求（公开网站、回调、邮件、游戏服务端），这家全线产品都不合适，出口只出不进是设计使然，不是套餐差异。

**mkcloud 和普通香港 VPS 有什么区别**

测评圈经常把这两类东西放一起比，其实它们不是同一个品类：

| 维度 | 普通公网香港 VPS | mkcloud 专线 VPS |
| --- | --- | --- |
| 跨境路径 | 走公网，晚高峰受国际出口拥堵影响 | IEPL/IPLC/IX 专线路径，端内 1~28ms（按线路） |
| IP | 多为共享段，易被平台风控关联 | 每台独立入口 IP + 独立出口 IP |
| 价格量级 | 几十元/月起 | ¥158~4500/月（共享流量），独享更高 |
| 合规 | 一般无实名要求 | 中国实名 + 省级白名单，禁机场/回国用途 |
| 用途 | 建站、代理皆可 | 只能 VPS 内向外访问，不能公开建站 |

一句话：普通 VPS 买的是“便宜”，mkcloud 卖的是“确定”，前者是公网尽力而为，后者是为跨境路径和独享 IP 付费。如果你只是想看视频、挂个轻应用，前者够用；如果你的业务靠这条链路吃饭，二者的价差其实好解释——有第三方实测把沪日共享流量折算成单向约 0.7~0.8 元/GB，跑业务的人自己能算这笔账。

**购买流程：五步走完**

1. 注册账号并完成实名（个人：手机号+姓名+身份证号；企业另有对公资料要求）。
2. 在产品页依次选地区→网络（入口）→类型（流量计费/独享带宽）→套餐→系统，直连款在附加选项里选“可连入省份”。
3. 购物车“优惠劵码”框填码并应用。
4. 选周期（月付/季付/半年付/年付/两年/三年），支付宝付款。
5. 现货一般约 1 分钟自动开通；上海 CN2 这类产品 7 天内交付，开通后按页面提示提交工单确认注意事项。

**下单前必须知道的几条限制**

这些全部来自官方页面原文，属于买了才发现就晚了的那类信息：

- **省级白名单**：直连款开通后只允许绑定省份的 IP 连入，跨省使用需要按官方流程处理；IX 不限省份但必须从支持的云厂网络接入。
- **退款规则**：仅质量问题支持退款，需要在工单里提交具体延迟、速度数据，由商家审核判断；商家自述口径为 24 小时内无质量问题不退款，且开通后不支持换地域。
- **超量与限速**：流量按双向统计，超量暂停（部分 IX 档位页面直接标注“超量停机”），可自助购买流量重置或工单补差价升级；第三方评测提到重置按原价 9折收费。
- **升降级**：都要走工单，降级到更低价套餐时差价不退；快照、备份不作为已提供的能力。
- **IP 预期**：出口是服务器 IP，不保证原生、住宅或流媒体解锁；官方知识库反复强调，独享 IP 也不等于平台账号一定不关联。

**mkcloud 靠谱吗：稳定性和售后情况**

商家自述运营以来上一年突发故障约 3 次（不含提前公告的维护），全部产品默认无 SLA，但可定制。官方 Telegram 通知群会实时发维护和故障公告，香港线路机房迁移那段时间，官方给全体香港专线用户延长了 1 天到期时间并补偿了迁移期间消耗的流量——出问题时有没有补偿、补偿多少，这些公告是可查的。

第三方实测方面，公开测评对广港 IEPL 的评价比较一致：端内延迟 2~4ms、晚高峰波动小；沪日方向有博主测得三网入口延迟 28~33ms。这家经常在官方渠道征集真实用户的测评投稿，搜集测评时注意区分“官方组织的体验文”和独立测试。想自己验证，官方知识库有专门的测速方法文章，分别测本地到入口、VPS 到目标两段，别把端内延迟当成你打开网站的全程耗时。

**常见问题**

**mkcloud 是机场吗？能当科学上网工具用吗？** 不是。它交付的是需要实名认证的云服务器/独立服务器，官方页面明确禁止机场、回国等违规用途，发现即清退不退款。

**为什么比普通 VPS 贵这么多？** 官方有专文解释：价格由出口方向、共享峰值或独享带宽、月流量、配置和接入成本构成，专线链路本身就不是公网带宽的成本结构。

**月付可以吗？** 可以，全线支持月付起，支付宝付款。对这类中等规模的商家，先月付跑一个月再决定年付，是风险最低的姿势。

**深港IX 158 元那个套餐我能直接买吗？** 能下单，但它只是专线那一半的价格——你必须同时有一台支持范围内的云厂服务器做前置，前置机的钱和带宽限制要自己算进去。没有云厂机器就选直连款。

**沪港 IPLC 和广港 IEPL 都到香港，选哪个？** 官方选型文给的口径：在广东、要最低价最低延迟选广港；业务已上云选深港 IX；在上海或做金融对港选沪港。先确认你的接入条件，再比价格。

**买错套餐能退吗？** 只有质量问题能退，且要拿数据说话。“买多了流量”“选错方向”这类原因不在退款范围内，下单前把月流量估算清楚。

最后收个尾：mkcloud 的套餐虽多，但选择逻辑其实就三层——先定出口方向（香港/日本/美国/国内优化），再定接入方式（本地直连还是云厂 IX），最后按用量在共享流量和独享带宽之间二选一。三层答案都有了，表格里对应的那一行就是你的菜。价格和活动码变动比较勤，下单前👉 [去商店把这几个码挨个试一遍](https://bit.ly/MKCLoud)，以结算页实价为准。
