# Zea · 航海贸易地图

FVTT v12 独立开发测试模组，当前 **0.4.2**。80×80 地下海地图、共享商队、港口贸易、Bonus/Cup、NPC 背景订单与日历。

## 界面安装

Setup → Add-on Modules → Install Module → Manifest URL：

```text
https://raw.githubusercontent.com/litchicalpis/zea-trade-map/main/module.json
```

完整 ZIP、SHA-256 与说明见 [v0.4.2 Pre-release](https://github.com/litchicalpis/zea-trade-map/releases/tag/v0.4.2)。不要用 Create Module 空壳或自动生成的 Source code ZIP。

0.4.2 修复 Journal 为创建 GM 自动加入 OWNER=3 后，新建战役报 PRIVATE_STORAGE_PERMISSION、GM 管理窗口渲染失败的问题。默认权限和所有非 GM／未知用户仍须 NONE，只允许已知 GM 保留非 NONE 权限；真实权限异常显示恢复提示，不自动更改权限或删除 Journal。保留 0.4.1 的 Dialog／JournalEntry 接口注入修复。

升级前备份 World，安装后重启 Foundry 并刷新全部客户端。旧版报错可能已留下完整战役 Journal，请优先「载入战役／接管 Authority」，不要删除存档或反复新建；存在多份时先核对目标。

HTTP 与 HTTPS 均支持，新战役无口令。format 2 明文压缩、协议 2 未签名；保留 User flag 写入来源校验、GM Authority、版本、原子保存和快照。贸易规则与配置指纹沿用 0.3.2，不改变卡量、价格、NPC 三轮周期或规则 RNG。0.4.0／0.4.1 升级本补丁不需要转换存档。

format 1 只读不覆盖，保留旧包及原口令，按 ZIP 内 README 使用 `tools/migrate-vault.mjs` 本地离线转换，再由 GM 明确导入新 Journal 副本。口令不进参数或仓库，旧 Journal 不删；旧规则 0.3.0／0.3.1 不自动迁移。

80项自动测试、131文件／17脚本及配置素材校验通过。新增回归覆盖 GM 自动 OWNER、既有战役载入、导入、角色降级、权限拒绝与异常管理页恢复。与海战 dev.11.1 同页非 loopback HTTP 的45项浏览器检查通过，但 Foundry API 为模拟对象；**0.4.2 尚待真实 World 复验。**

仅用于封闭可信测试会话；gzip/base64 不是加密，未签名消息不能抗主动伪造，HTTP 不保护登录凭据。**真实 World 首轮联调发现玩家可读取完整 Journal flags；本补丁不解决该读取隔离，验收仍未通过。** 所有 GM／玩家须同步升级刷新，不能混用协议 1／2。

默认分支只托管 README 和清单；客户端代码、完整资源、离线工具与文档在 Release 安装 ZIP 中。旧附件保留。素材沿用用户项目与原来源记录，不额外授予再分发许可。发布不会自动更新 Foundry 服务器，此 Pre-release 渠道不是生产验收声明。
