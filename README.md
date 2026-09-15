# Zea · 航海贸易地图

Foundry VTT v12 的独立航海贸易地图模组发布仓库。当前测试预发布：**0.3.2**。

提供 80×80 地下海地图、共享商队、沦敦卡 3/2/2、NPC 采购后三轮交付、Bonus Cup、日历及港口图鉴。不依赖海战模块或外部裁决服务器。

## 纯界面安装

Foundry Setup → Add-on Modules → Install Module → Manifest URL：

```text
https://raw.githubusercontent.com/litchicalpis/zea-trade-map/main/module.json
```

安装后在独立测试 World 的「管理模组」启用，按 **Shift+T** 打开。首次建立战役须输入至少 12 字符的存档口令；请妥善保管，遗失口令无法恢复加密存档。

本仓库仅存放安装入口与说明；完整模块代码、配置、素材和详细手册在 [Release 安装包](https://github.com/litchicalpis/zea-trade-map/releases/tag/v0.3.2) 中。不要下载 GitHub 自动生成的 Source code ZIP 作为模组安装包。

`main/module.json` 是开发测试更新渠道，固定版本清单也随 Release 提供。Pre-release 不依赖 `releases/latest` 路由；更新前先检查说明。

## 测试与升级边界

- 57 项本地自动测试与打包检查通过；真实 FVTT v12 多客户端、服务器重启、权限隔离及与海战模组共同启用的验收尚未完成。
- 旧版 0.3.0/0.3.1 战役不自动迁移；升级前备份 World、旧包和存档口令，勿删除旧加密 Journal。
- 运行需 HTTPS 或 localhost 安全来源，以及支持 Web Crypto / CompressionStream 的现代浏览器。
- 服务器必须能匿名访问 GitHub、raw.githubusercontent.com 及 Release 下载域名。
- 保留随包港口美术的来源、原图与校验信息；既有素材的版权与使用范围以原权利人为准，本项目不额外授予再分发许可。
- 不发布真实 World、战役存档、口令、浏览器资料、分析脚本或工作区其他项目。
