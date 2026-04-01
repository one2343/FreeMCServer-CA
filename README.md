# 🎮 FreeMCServer 自动续期

自动完成 [FreeMCServer.net](https://freemcserver.net) 的服务器续期，并在服务器停止时自动启动，运行于 GitHub Actions。

---

## ✨ 功能

- 🔄 每 3 小时自动续期，支持手动触发
- 🛡️ 内置广告猎手，常驻拦截广告元素
- ✅ 自动处理 Cloudflare Turnstile 验证
- 🚀 续期后检测服务器状态，自动启动
- 👥 监控玩家上线直到就绪
- 📨 Telegram 推送续期结果

---

## ⚙️ 配置

在仓库 **Settings → Secrets** 中添加以下变量：

| Secret | 说明 |
|--------|------|
| `FMCS_ACCOUNT` | 账号信息，格式：`邮箱,密码` |
| `FMCS_SERVER_ID` | 服务器 ID，例如：`1992440` |
| `TG_BOT` | Telegram 推送，格式：`chat_id,bot_token` |
| `GOST_PROXY` | 代理地址，例如：`socks5://user:pass@host:port`（可选）|
| `PRIVATE_REPO_TOKEN` | 私库访问 Token |

---

## 📁 文件结构

```
公库/
├── .github/workflows/freemcserver-renew.yml   # Actions 工作流
└── README.md

私库 FreeMCServer-Renew-Private/
└── renew.py                                   # 续期脚本
```

---

## 📨 TG 通知示例

```
✅ FreeMCServer 续期成功
🖥 服务器: maribel
⏱️ 续期后: 3 hours, 59 minutes, 54 seconds.
🟢 服务器状态: Server is online
👥 当前玩家数: 3
```
