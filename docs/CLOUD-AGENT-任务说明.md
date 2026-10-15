# Cloud Agent · 任务说明（复制下面「任务块」）

## 任务块（粘贴到 Cloud Agent）

```text
工作目录：当前仓库（CursorCloud竞品拆解）。禁止读取或引用 sample-wms、QWMS-Coding、任何内网 GWMS。

目标竞品：[竞品名称]
Base URL：[https://...]
本次模块：[例如：出库单列表 + 创建]
测试账号：我会在浏览器/login 步骤配合；不要把密码写入仓库或对话持久化。

手段：
1. 用 Playwright（或 browser MCP）只走主路径，不要全站爬虫。
2. 每完成一步：snapshot + 必要时截图，存 notes/ 或 screenshots/（脱敏）。
3. 按 docs/TEMPLATE-竞品拆解.md 新建 notes/YYYY-MM-DD-[竞品]-[模块].md 并填写。

输出要求：
- 业务拆解：流程、页面、字段、可见校验、Tab/状态。
- 每条规则标「证据：第几步 / 截图文件名」。
- 不知道的写进「未确认」，不要猜后台逻辑。

禁止：
- 逆向二进制、全量 REA MCP。
- 修改竞品系统数据（仅只读走查；除非我明确说用测试号可造数）。
- 把结论写成「千易/GWMS 现网口径」。

完成时简短汇总：新建了哪些文件、哪些步骤因登录/验证码阻塞需我人工处理。
```

## 登录搞不定时

- 你在本机浏览器先登录竞品测试环境，再让 Agent 使用 **storage state**（文件只放本地，已 gitignore）或分步「你点登录，Agent 从登录后 URL 继续」。
- 不要把 Cookie 文件 commit。

## 与 sample-wms 衔接

拆解完成后，你在 **sample-wms** 新对话里说：「根据竞品 notes/xxx.md，讨论 [功能] 范围，不写现网结论。」
