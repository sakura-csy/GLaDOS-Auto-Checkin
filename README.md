# 📌 GLaDOS  自动签到

一个基于 **GitHub Actions** 的 **GLaDOS 自动签到脚本**。
 **无需服务器、无需编程基础**，每天自动帮你签到。

------

## ✨ 功能说明

- ✅ **每天自动签到**
- 🔁 **已签到自动识别，不会报错**
- 👥 **支持多个账号**
- 📬 **可选签到结果推送（PushDeer）**
- 🆓 **完全免费，使用 GitHub Actions**

------

## 📂 项目结构

```
.
├── checkin.py                 # 签到脚本（不用动）
└── .github/workflows/
    └── glados.yml              # GitHub Actions 配置（不用动）
```

------

## 🚀 使用教程

### 第一步：Fork 本项目

1. 点击右上角 **Fork**
2. Fork 到你自己的 GitHub 账号下

👉 后续所有操作都在你 **自己的仓库** 中完成

------

### 第二步：获取 GLaDOS Cookie

1. 打开浏览器，登录：https://glados.cloud
2. 按 **F12** 打开开发者工具
3. 找到：
   - Chrome：`Application` → `Cookies`
   - Firefox：`存储` → `Cookies`
4. 选择 `glados.cloud`
5. **复制完整 Cookie 内容**

示例（示意）：

```
koa:sess=xxxxxx; koa:sess.sig=yyyyyy
```

⚠️ **必须是完整的一整段，不要只复制一半**

------

### 第三步：添加 GitHub Secrets

进入你 Fork 后的仓库：

1. 点击 **Settings**
2. 左侧选择 **Secrets and variables → Actions**
3. 点击 **New repository secret**

#### 添加第一个 Secret（必填）

- **Name**：`COOKIES`
- **Value**：粘贴刚才复制的 Cookie

点击 **Save**

------

### （可选）第四步：开启签到结果推送

如果你想每天收到签到通知（可选）：

1. 注册 PushDeer：https://www.pushdeer.com
2. 获取你的 `SENDKEY`
3. 在 GitHub Secrets 中再添加一个：

- **Name**：`SENDKEY`
- **Value**：你的 PushDeer key

不填也没关系，只是不会推送。

------

## 👥 多账号如何添加？

### 规则很简单：

> **多个账号的 Cookie，用 `&` 连接**

示例：

```
cookie_账号1 & cookie_账号2 & cookie_账号3
```

⚠️ 注意事项：

- 不要换行
- 不要用逗号
- 每个 cookie 都是完整的一段

------

## ⏰ 自动签到时间说明

项目默认设置为：

```
每天 UTC 06:00 自动运行
```

换算成北京时间：

> 🕛 **每天中午 14 点自动签到**

你无需做任何操作，它会每天自动运行。
