---
layout:     post
title:      "区块链原理与去中心化应用实战"
subtitle:   "区块链技术的核心概念和原理（一）"
date:       2018-07-03 09:00:00
author:     "HanLu"
header-img: "img/post-blockchain-1.1.jpg"
header-mask: 0.3
catalog:    true
tags:
    - 区块链
---

## 区块链的前世今生

### 密码朋克（Cypherpunk）

维基解密的创始人：阿桑奇

BT下载的作者：布莱姆-科恩

WWW的发明者：蒂姆伯纳斯-李

智能合约概念的提出者：尼克萨博

Facebook的创始人：肖恩帕克

中本聪

* Adam Back发明了Hashcash，使用了POW

* Haber/Stornetta提出时间戳方法保证数字文件安全的协议

* 戴伟发明了B-money，强调点对点交易和不可更改记录

* 哈尔-芬尼推出了“加密现金”

* 2008年中本聪《比特币：一个点对点的电子现金系统》

## 区块链的应用场景

资产：数字资产的发行，支付（跨境支付），交易，结算

记账：股权交易，供应链金融，商业积分

不可篡改：溯源，众筹，医疗证明，存在性证明

点对点：共享经济，物联网

隐私：匿名交易

## 比特币

货币：凯恩斯《货币论》：货币是可以承载价值的一般等价物（铜币，金银，银票，法币）

比特币：数字货币，财产只受自己(私钥)控制，无通胀，没有假钞，流通性好，去中心化的记账系统。

![](/img/in-post/post-blockchain-1/post-blockchain-1.1.jpg)

### 比特币原理

账本如何验证：

## Hash

哈希函数：Hash（原始信息）= 摘要信息

同样的原始信息用同一个哈希函数总能得到相同的摘要信息

原始信息任何微小的变化都会哈希出面目全非的摘要信息

从摘要信息里无法逆向推算出原始信息

区块：

![](/img/in-post/post-blockchain-1/post-blockchain-1.2.jpg)

账户所有权：

账号->地址

![](/img/in-post/post-blockchain-1/post-blockchain-1.3.jpg)

密码->私钥

![](/img/in-post/post-blockchain-1/post-blockchain-1.4.jpg)

## 非对称加密技术（交易签名）

交易进行hash得到摘要

用私钥对摘要进行签名

![](/img/in-post/post-blockchain-1/post-blockchain-1.5.jpg)

![](/img/in-post/post-blockchain-1/post-blockchain-1.6.jpg)

![](/img/in-post/post-blockchain-1/post-blockchain-1.7.jpg)

![](/img/in-post/post-blockchain-1/post-blockchain-1.8.jpg)

为什么记账：

记账：Hash打包过程，需消耗资源，得到奖励。

挖矿-工作量证明

规则：一段时间只有一人可以记账成功

通过解决密码学难题（即工作量证明）竞争获得唯一记账权

其它节点复制记账结果

工作量证明：Hash(上一个交易摘要，交易记录集，随机数) == 若干个0开头的 ash

交易记录集：收集广播中还没有被记录账本的交易，交易的有效性验证，添加一笔给自己转账的交易（挖矿奖励）

## 共识机制

两个节点同时完成工作量证明，使用谁的区块？ 无仲裁机构裁决

为什么要遵守协议？ 节点工作量只有在其他的节点认同其是有效的

* 累计工作量最大的区块链（独立，延长最长链）

![](/img/in-post/post-blockchain-1/post-blockchain-1.9.jpg)
