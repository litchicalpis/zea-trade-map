# Zea · 航海贸易地图

FVTT v12 独立开发测试模组，当前 **0.4.1**。80×80 地下海地图、共享商队、港口贸易、Bonus/Cup、NPC 背景订单与日历。

## 界面安装

Setup → Add-on Modules → Install Module → Manifest URL：

```text
https://raw.githubusercontent.com/litchicalpis/zea-trade-map/main/module.json
```

完整 ZIP、SHA-256 与说明见 [v0.4.1 Pre-release](https://github.com/litchicalpis/zea-trade-map/releases/tag/v0.4.1)。不要用 Create Module 空壳或自动生成的 Source code ZIP。

0.4.1 修复新建战役时报 `Cannot read properties of undefined (reading 'confirm')`：启动入口显式传入 v12 的 Dialog、JournalEntry 等接口，覆盖创建存档、贸易和管理确认及地图背叛弹窗。已安装用户经 Setup 检查更新，重启 Foundry 并刷新全部客户端后复测。

HTTP 与 HTTPS 均支持，新战役无口令。format 2 明文压缩、协议 2 未签名；保留 User flag 写入来源校验、GM Authority、版本、原子保存和快照。贸易规则与配置指纹沿用 0.3.2，不改变卡量、价格、NPC 三轮周期或规则 RNG。0.4.0 升级本补丁不需要转换存档。

升级先备份 World、旧包和原口令；format 1 只读不覆盖，按 ZIP 内 README 使用 `tools/migrate-vault.mjs` 本地离线转换，再由 GM 明确导入新 Journal 副本。口令不进参数或仓库，旧 Journal 不删；旧规则 0.3.0／0.3.1 不自动迁移。

74 项自动测试、131 文件／17 脚本及配置素材校验通过。新增回归加载实际启动入口并模拟 v12 词法全局类，验证取消不写入、确认创建246实例并保存Journal，以及地图背叛。与海战 dev.11 同页真实非 loopback HTTP 的45项浏览器检查通过，但 Foundry API 为模拟对象；**真实 FVTT 权限、多 GM、重启、共同启用仍待验收。**

仅用于封闭可信会话；gzip/base64 不是加密，未签名消息不能抗主动伪造，HTTP 不保护登录凭据。所有 GM／玩家须同步升级刷新，不能混用协议 1／2。

默认分支只托管 README 和清单；客户端代码、完整资源、离线工具与文档在 Release 安装 ZIP 中。旧附件保留。素材沿用用户项目与原来源记录，不额外授予再分发许可。此 Pre-release 渠道不是生产验收声明。
