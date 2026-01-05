# CF-Workers-SUB-Modified

基于 [cmliu/CF-Workers-SUB](https://github.com/cmliu/CF-Workers-SUB) 修改的 Cloudflare Workers 订阅聚合与转换工具。

## ⚙ 功能特点

- 🔗 **订阅聚合** - 将多个订阅源合并为一个订阅链接
- 🔄 **格式转换** - 支持 Base64、Clash、Sing-box、Surge、Quantumult X、Loon 等多种格式
- 📱 **多订阅管理** - 支持创建多个独立的子订阅（sub1, sub2...）
- 🌐 **优选 IP** - 支持自定义优选 IP/域名替换节点地址
- 💾 **KV 存储** - 使用 Cloudflare KV 存储配置数据
- 🎨 **现代化 UI** - 响应式设计，支持明暗主题

---

## 🛠️ 部署方法

### 1. 部署 Cloudflare Worker

- 在 [Cloudflare Dashboard](https://dash.cloudflare.com/) → Workers & Pages 中创建一个新的 Worker
- 将 [worker.js](worker.js) 的内容粘贴到 Worker 编辑器中并保存

### 2. 设置环境变量

在 Worker 设置 → 变量 中添加：

| 变量名 | 示例 | 必填 | 备注 |
|--------|------|:----:|------|
| `TOKEN` | `your-secret-token` | ✅ | 管理员访问令牌，建议使用复杂字符串 |

### 3. 绑定 KV 命名空间（强烈推荐）

> ⚠️ **重要**: 强烈建议绑定 KV！不绑定的话每次修改订阅都需要改代码重新部署。

| 功能 | 无 KV | 有 KV |
|------|:-----:|:-----:|
| 在线编辑订阅 | ❌ 需改代码 | ✅ 网页直接编辑 |
| 多订阅管理 | ❌ 不支持 | ✅ 支持 sub1/sub2/... |
| 配置持久化 | ❌ | ✅ KV 永久存储 |

**绑定步骤：**
1. Cloudflare Dashboard → Workers & Pages → KV → 创建命名空间
2. 进入你的 Worker → 设置 → 变量 → KV 命名空间绑定
3. 添加绑定，**变量名必须为 `KV`**
4. 保存即可

### 4. 开始使用

- **管理面板**: `https://your-worker.workers.dev/{TOKEN}`
- **订阅地址**: `https://your-worker.workers.dev/?token={TOKEN}`

---

## 🔧 主要修改

相比原项目，本版本进行了以下修改：

- 移除了部分硬编码的外部资源引用
- 优化了部分代码结构

---

## 📜 许可证

本项目采用 [Apache-2.0](LICENSE) 许可证开源。

## 🙏 致谢

- [cmliu/CF-Workers-SUB](https://github.com/cmliu/CF-Workers-SUB) - 原项目
