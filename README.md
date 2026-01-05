# CF-Workers-SUB (Modified)

基于 [cmliu/CF-Workers-SUB](https://github.com/cmliu/CF-Workers-SUB) 修改的 Cloudflare Workers 订阅聚合与转换工具。

## ⚙ 功能特点

- 🔗 **订阅聚合** - 将多个订阅源合并为一个订阅链接
- 🔄 **格式转换** - 支持 Base64、Clash、Sing-box、Surge、Quantumult X、Loon 等多种格式
- 📱 **多订阅管理** - 支持创建多个独立的子订阅（sub1, sub2...）
- 🌐 **优选 IP** - 支持自定义优选 IP/域名替换节点地址
- 💾 **KV 存储** - 使用 Cloudflare KV 存储配置数据
- 🎨 **现代化 UI** - 响应式设计，支持明暗主题

## 📦 部署方法

### Workers 部署

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 进入 Workers & Pages
3. 创建新的 Worker
4. 复制 `worker.js` 的内容并保存
5. 设置环境变量（见下方说明）

### 环境变量

| 变量名 | 说明 | 必填 |
|--------|------|------|
| `TOKEN` | 管理员访问令牌 | ✅ |
| `GUESTTOKEN` | 访客订阅令牌 | ❌ |
| `KV` | 绑定的 KV 命名空间 | ❌ |
| `SUBAPI` | 订阅转换后端地址 | ❌ |
| `SUBCONFIG` | 订阅配置文件 URL | ❌ |
| `TGTOKEN` | Telegram Bot Token | ❌ |
| `TGID` | Telegram Chat ID | ❌ |

## 🔧 主要修改

相比原项目，本版本进行了以下修改：

- 移除了部分硬编码的外部资源引用
- [在此添加你的其他修改内容]

## 📜 许可证

本项目采用 [Apache-2.0](LICENSE) 许可证开源。

## 🙏 致谢

- [cmliu/CF-Workers-SUB](https://github.com/cmliu/CF-Workers-SUB) - 原项目
