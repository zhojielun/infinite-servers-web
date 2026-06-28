# Infinite Servers — 配置生成工具

纯前端静态页面，用于生成 `servers.json` 和 `config.json` 配置文件。

## 使用

```bash
# 本地预览
cd ~/infinite-servers-web
python3 -m http.server 8080
# 浏览器打开 http://localhost:8080
```

或部署到任意静态托管（GitHub Pages、Cloudflare Pages 等）。

## 页面

| 页面 | 功能 |
|------|------|
| `index.html` | 首页导航 |
| `servers/index.html` | 服务器列表配置 — 添加/编辑服务器节点，生成 `servers.json` |
| `config/index.html` | 全局配置 — 密码、SSE、历史保留、CORS、Telegram 通知 |

## 特性

- 所有数据保存在浏览器 localStorage，无需后端
- 实时 JSON 预览，支持直接编辑 JSON 同步回表单
- IPv4 / IPv6 IP 遮罩分别配置
- 输入 2 位地区代码（如 `CN`）自动填充国家名称
- 随机 Token 一键生成
- 深色/浅色主题切换
- 一键复制、下载 JSON 文件
- Cloudflare Pages 部署兼容（相对路径链接）

## Telegram 配置项

config.json 页面支持完整的 Telegram 通知配置：

| 配置项 | 默认值 | 说明 |
|--------|--------|------|
| Bot Token | — | Telegram Bot Token |
| Chat ID | — | Telegram Chat ID |
| 到期检查 Cron | `0 0 * * *` | 到期提醒检查频率 |
| 离线检查 Cron | `*/5 * * * *` | 离线告警检查频率 |
| 离线阈值 | `900` | 超过此秒数未上报视为离线 |
| 离线告警 | 关闭 | 是否启用离线通知 |
| 提醒语言 | English | 消息语言（中文/英文） |
