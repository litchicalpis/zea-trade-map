# Zea · 航海贸易地图

Foundry VTT v12 独立测试模组，当前 **0.5.0 Pre-release**。80×80地下海地图、共享商队「重装SS Sharknado」、港口贸易、Bonus/Cup、NPC背景订单与日历。

## 安装与更新

Setup → Add-on Modules → Install Module → Manifest URL：

```text
https://raw.githubusercontent.com/litchicalpis/zea-trade-map/main/module.json
```

完整安装包、清单和校验表见 [v0.5.0 Release](https://github.com/litchicalpis/zea-trade-map/releases/tag/v0.5.0)。默认分支仅托管README和更新清单，完整代码、资源、工具和说明均在Release安装ZIP中。不要使用自动生成的Source code ZIP；旧Release保留。Word玩家手册只在本地保存，不在仓库或Release中发布。

## 本版修改

- 同港同商品可有两枚特需，每港仍最多两枚、全图十二枚。每张货物至多匹配一枚；不采用一张货物叠加全部奖金的规则。
- 迷雾与已揭示海洋同色、完全不透明；精确模式#F3F0E7，离散模式#E9E2CD。未探索地形、港口和地点仍不进入玩家视图。
- 蘑菇酒普通／1882／1868／1844买价20／30／40／60，基础卖价60／90／120／180 Echo，均占5 Cargo。奖金仍按普通批次基准计算。
- 当前Authority可在GM管理中指定Cup与货舱中的商品卡互转：添加必须来自Cup，移除直接回Cup，合计不超过40 Cargo。不改变Echo、日期或RNG、不抽替补；操作前保存快照。添加货物不视为采购，不享受跨港特需。
- Cup初始32枚，手动转移后按净移入数增减；普通交易仍等量进出，总实例仍246。

## 旧战役升级

规则Schema升级为5；**0.3.2–0.4.5旧战役不会自动覆盖**。先备份World，再在GM管理导出原始存档封装，使用安装包 `tools/migrate-rules.mjs` 离线转换，最后导入新副本。保留实例、Echo、日期、航线、RNG及所有快照；既有陈酿今后按新价出售，旧账不重算。加密format1使用 `tools/migrate-vault.mjs` 和原口令转换；0.3.0/0.3.1不支持本次迁移。详见包内 `docs/UPGRADE-0.5.0.md`。

## 验证与边界

100项自动测试、136文件／19脚本打包检查、78项非回环HTTP双包浏览器检查通过。浏览器使用模拟Foundry API，不代表真实World、权限或服务器网络验收。发布不自动更新Foundry服务器；请备份并在独立测试World复验，全部GM／PC一起更新刷新。

支持HTTP和HTTPS；format2明文压缩、协议2未签名，只适合可信会话，不承诺原始Journal保密或抗恶意客户端。素材沿用原来源与权利，不额外授予再分发许可。
