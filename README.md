# Background Remover 部署指南

## 文件结构

```
background-remover/
├── worker.js      # Cloudflare Workers 后端
├── index.html     # 前端页面
├── wrangler.toml  # 部署配置
└── README.md      # 本文件
```

## 快速部署

### 1. 安装 Wrangler CLI

```bash
npm install -g wrangler
```

### 2. 登录 Cloudflare

```bash
wrangler login
```

### 3. 设置 API Key

```bash
wrangler secret put REMOVE_BG_API_KEY
# 输入你的 Remove.bg API Key
```

### 4. 部署 Workers

```bash
cd background-remover
wrangler deploy
```

### 5. 绑定前端

Workers 默认只能处理 API 请求。要托管前端页面，有两种方式：

**方式 A：Workers Sites（推荐）**
```bash
wrangler pages deploy .
```

**方式 B：结合 Cloudflare Pages**
1. 创建 Cloudflare Pages 项目
2. 上传 `index.html`
3. Workers 作为 API 后端

## 获取 Remove.bg API Key

1. 访问 https://www.remove.bg/api
2. 注册账号
3. 免费版：50次/月

## 本地开发

```bash
wrangler dev
```

访问 http://localhost:8787 测试
