# Zea · 航海贸易地图

FVTT v12 独立开发测试模组，当前 **0.4.5**。80×80 地下海地图、重装SS Sharknado 商队、港口贸易、Bonus/Cup、NPC 背景订单与日历。

## 安装与更新

Setup → Add-on Modules → Install Module → Manifest URL：

```text
https://raw.githubusercontent.com/litchicalpis/zea-trade-map/main/module.json
```

完整安装包、校验表和说明见 [v0.4.5 Pre-release](https://github.com/litchicalpis/zea-trade-map/releases/tag/v0.4.5)。不要使用 Create Module 空壳或 GitHub 自动生成的 Source code ZIP。默认分支仅托管 README 和更新清单，完整代码、资源及说明在 Release 安装 ZIP；旧 Release 保留。

## 本版修改

- 展示完整下层舱室的 140 格，包括艏部储藏、主货舱、煤舱、锅炉、三胀主机、轴隧和三处楼梯。
- 上方立柱改为 (13,7)、(17,7)，与第 10 行对称。实际商品和补给每 cargo 占 1.5 格，避开主货舱立柱和楼梯。
- 同类货物共用一个包络和一个标注，保留空洞；同色 3px 边框，填充透明度 70%（不透明度 30%）。原交易规则不变。
- 移除冗余标注及独立航线 JSON，获授权的玩家直接移动并自动留轨迹。合并未单独发布的全屏地图、适配全图及标题栏对比度修复。
- 当前 Authority 可在 GM 管理中初始化地图：回到初始日期、地图、Cup、卡牌与遮罩，清空全部旧战役 Journal、快照及交易／移动／请求记录。新建战役恢复建档起点、资金和补给；旧存档按确认提示使用默认值。
- 正式船名统一为「重装SS Sharknado」，与海战模组一致。

**初始化不可撤销，且不会创建恢复快照。** 保留 Authority 和 PC 授权；已下载到电脑、Foundry 服务器外部备份中的资料不受模组控制。请先单独备份要保留的资料。初始化只限当前 Authority 会话，其他 GM、PC 及失效会话不能执行。

## 验证与边界

91 项自动测试、133 文件／19 脚本打包检查及 67 项双包浏览器检查通过；非回环 HTTP 下无需原生 UUID 或 subtle。浏览器使用模拟 Foundry API，不代表真实 World 的初始化、权限或多人网络验收。请在独立测试 World 交付 PC 复验。

HTTP 与 HTTPS 均支持，format 2 为明文压缩、协议 2 未签名；不承诺原始 Journal 保密、抗恶意客户端或网络篡改。贸易规则、配置指纹与卡牌数量保持不变。旧 format 1 只读不覆盖，先保留旧包及原口令，再按安装包 README 离线转换；不自动迁移旧规则。

升级前备份 World，全部 GM／PC 一起刷新，勿混用旧客户端。发布不会自动更新 Foundry 服务器。素材沿用项目原来源记录，不额外授予再分发许可。
