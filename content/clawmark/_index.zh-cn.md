---
title: "ClawMark"
description: "标注任意网页，即时分享反馈。"
weight: 1
layout: "product"
---

<div class="product-hero">
  <span class="badge" id="cm-badge">浏览器扩展 + 可嵌入 Widget &middot; <span id="cm-version">加载中...</span></span>
  <h1>ClawMark</h1>
  <p class="tagline">
    标注任意网页。高亮文本、添加评论，一键将反馈发送到 GitHub Issues、Lark、Telegram、Slack 或邮件。
  </p>
  <div class="hero-actions">
    <a href="https://labs.coco.xyz/clawmark/dashboard/" target="_blank" class="btn-primary">打开 Dashboard &rarr;</a>
    <a href="https://github.com/coco-xyz/clawmark/releases" target="_blank" class="btn-secondary">下载扩展</a>
  </div>
</div>

<div class="features-section">
  <h2>核心功能</h2>
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon">&#128269;</div>
      <h3>浏览器扩展</h3>
      <p>Chrome Extension (MV3)，支持页内文本高亮和标注。选择文本、写下想法、提交——一步到位。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128296;</div>
      <h3>可嵌入 Widget</h3>
      <p>只需在网站插入一行 script 标签，即可收集访客反馈，无需安装任何东西。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128640;</div>
      <h3>灵活路由</h3>
      <p>将标注发送到 GitHub、Lark、Telegram、Slack、邮件、Linear、Jira、HxA Connect 或自定义 Webhook。支持优先级规则路由。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128275;</div>
      <h3>开源</h3>
      <p>可自托管服务端，也可使用官方托管服务。完全掌控你的数据和集成。</p>
    </div>
  </div>
</div>

<div class="quickstart-section">
  <h2>快速开始</h2>

### 安装

1. 从 [GitHub Releases](https://github.com/coco-xyz/clawmark/releases) 下载最新版本
2. 打开 `chrome://extensions/`，开启**开发者模式**
3. 点击**加载已解压的扩展程序**，选择扩展文件夹
4. 点击工具栏 ClawMark 图标，使用 **Google 登录**

### 使用方式

在任意网页上选中文本，浮动工具栏会自动出现。点击**评论**或**问题**即可创建标注。ClawMark 会根据你的投递规则自动路由到对应的目标。

```
   你的标注             ClawMark 服务器          投递目标
┌─────────────┐     ┌────────────────┐     ┌──────────────────┐
│  选中文本    │────▶│ 收集 & 存储     │────▶│ GitHub Issues    │
│  添加评论    │     │ 解析规则        │     │ GitLab Issues    │
│  提交        │     │ 分发            │     │ Lark / Telegram  │
└─────────────┘     └────────────────┘     │ Slack / 邮件     │
                                            │ Webhook          │
                                            └──────────────────┘
```

### 路由规则

ClawMark 按以下优先级决定标注的投递目标：

1. **URL 匹配规则** — 你定义模式如 `*github.com/myorg/*` → GitHub Issues
2. **自动检测** — 在 GitHub 页面上自动识别仓库并创建 Issue
3. **默认目标** — 你设置的兜底投递渠道
4. **系统默认** — 服务端配置的全局默认

在 **Dashboard** 中管理规则、凭证和查看你的标注（点击扩展图标 → 打开面板）。

### 公共服务器

官方托管服务器地址：**`https://api.coco.xyz/clawmark`** — 无需任何配置，安装扩展即可使用。

### 自托管服务端

```bash
git clone https://github.com/coco-xyz/clawmark.git
cd clawmark
npm install
npm start
```

将扩展指向你的服务器：扩展图标 → 设置 → 连接 → 输入服务器 URL。

</div>

<div id="cm-release" class="features-section" style="display:none;">
  <h2>最新版本</h2>
  <div style="background:var(--tw-prose-pre-bg,#1e1e2e);border-radius:8px;padding:1.5rem;color:var(--tw-prose-body,#cdd6f4);">
    <div style="display:flex;align-items:center;gap:0.75rem;margin-bottom:0.75rem;">
      <strong id="cm-rel-name" style="font-size:1.2rem;"></strong>
      <span id="cm-rel-date" style="opacity:0.6;font-size:0.85rem;"></span>
    </div>
    <div id="cm-rel-body" style="white-space:pre-wrap;font-size:0.9rem;line-height:1.6;max-height:300px;overflow-y:auto;"></div>
    <div style="margin-top:1rem;">
      <a id="cm-rel-link" href="#" target="_blank" style="color:#89b4fa;">在 GitHub 查看 &rarr;</a>
    </div>
  </div>
</div>

<div class="bottom-links">
  <a href="https://labs.coco.xyz/clawmark/dashboard/" target="_blank">Dashboard &nearr;</a>
  <a href="https://github.com/coco-xyz/clawmark" target="_blank">GitHub &nearr;</a>
  <a href="https://github.com/coco-xyz/clawmark/releases" target="_blank">Releases &nearr;</a>
  <a href="https://github.com/coco-xyz/clawmark/issues" target="_blank">Issues &nearr;</a>
  <a href="/clawmark/privacy/" target="_blank">隐私政策 &nearr;</a>
</div>

<script>
(function() {
  fetch('https://api.github.com/repos/coco-xyz/clawmark/releases/latest')
    .then(function(r) { return r.json(); })
    .then(function(d) {
      if (!d.tag_name) return;
      var v = d.tag_name.replace(/^v/, '');

      // 更新版本号
      document.getElementById('cm-version').textContent = 'v' + v;

      var body = (d.body || '').replace(/\r\n/g, '\n');
      var sec = document.getElementById('cm-release');
      if (sec) {
        sec.style.display = '';
        document.getElementById('cm-rel-name').textContent = d.name || d.tag_name;
        document.getElementById('cm-rel-date').textContent = new Date(d.published_at).toLocaleDateString('zh-CN', {year:'numeric',month:'long',day:'numeric'});
        document.getElementById('cm-rel-body').textContent = body;
        document.getElementById('cm-rel-link').href = d.html_url;
      }
    })
    .catch(function() {
      document.getElementById('cm-version').textContent = 'v0.6';
    });
})();
</script>
