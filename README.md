# Cursor Cloud · 竞品拆解（纯 Web）

与 **sample-wms / QWMS** 完全分离。只做竞品观察与业务拆解，不作为自家现网口径。

## 工作方式

1. 在本目录用 **Cloud Agent** 开任务（或本机 Agent，但勿 @ 其他仓库）。
2. 用 **Playwright** 走竞品 Web 主路径（列表 → 创建/详情 → 关键弹窗）。
3. 产出写入 `notes/`，格式见 `docs/TEMPLATE-竞品拆解.md`。
4. 需要写自家需求时：在本机 **sample-wms** 对话里手工摘要点，**不要**自动同步进 specs。

## 信息安全（必守）

- 只用 **竞品测试账号**；密码、Cookie **不要**进 Git（见 `.gitignore`）。
- **不要**在本仓库放：QWMS 地址、内网 URL、sample-wms PRD、客户真实数据。
- 截图入库前检查：货主名、单号、地址、库存量须脱敏或打码。
- GitHub 建议 **Private** 仓库；专用账号与 work 账号分离。

## GitHub（独立账号）

在本目录终端（已登录 `wangyssky@gmail.com` 对应 GitHub）：

```bash
git init
git add .
git commit -m "init: competitor research workspace"
gh repo create cursor-cloud-competitor --private --source=. --push
```

首次使用 `gh` 需：`gh auth login` 选 GitHub.com，登录该账号。

## Cloud Agent 任务入口

复制 `docs/CLOUD-AGENT-任务说明.md` 里「任务块」，填竞品名与 URL 后粘贴到 Cloud Agent。
