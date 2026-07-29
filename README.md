# 长得好 · 农业研究工作台

农业研究者的桌面/手机 App，单文件 PWA。

## 📁 文件结构

```
workspace/
├── index.html          主应用（所有数据在本地的 localStorage 里）
├── manifest.json       PWA 配置文件
├── sw.js               Service Worker 离线缓存
├── icon-192.png        桌面图标
├── icon-512.png        PWA 启动屏图标
└── apple-touch-icon.png  iOS 图标
```

## 🚀 三种使用方式

### 方式一：本地双击打开（最快）
直接双击 `index.html`，浏览器打开就能用。
> ⚠️ 局限：PWA 离线缓存、Service Worker 在 `file://` 协议下不生效，但功能完全可用。

### 方式二：本地启动一个静态服务器（推荐 PWA 体验）
进入目录后：
```bash
python3 -m http.server 8000
```
浏览器访问 `http://localhost:8000`，即可"添加到主屏幕"做成 App。

### 方式三：部署到云端（任何设备都能访问）
免费方案：
- **Vercel**：拖入文件夹，30 秒生成网址
- **Netlify**：同上
- **GitHub Pages**：推送到 GitHub 仓库，`Settings → Pages` 启用

部署后得到一个网址（如 `https://changdehao.vercel.app`），所有设备访问都是同一份数据（实际数据仍在各自设备 localStorage）。

## 📱 安装为 App

**iOS Safari**：访问网址 → 底部分享按钮 → "添加到主屏幕"
**Android Chrome**：访问网址 → 右上角菜单 → "添加到主屏幕"
**桌面 Chrome/Edge**：地址栏右侧会显示一个"安装"图标

## 💾 数据备份

界面"每日任务"页面底部有 ⬇️ 导出数据 / ⬆️ 导入数据 按钮，定期导出 JSON 文件即可备份。

## 🧬 功能

- **遗传转化**：项目卡片，可加载体（DN001/DN122/DN127），每个项目独立记录进展
- **分子**：自由记录 PCR/电泳/测序等实验
- **种植**：按作物（辣椒/番茄/小麦）累计种植数 + 流水记录
- **每日任务**：
  - 周三 🌶️ 萌发辣椒种子
  - 周五 🍅 萌发番茄种子 + 🔍 转筛选
  - 每次"转筛选"完成后，自动在第 21/42/63... 天生成"继代"任务
  - 点击即可打勾完成，状态持久化
