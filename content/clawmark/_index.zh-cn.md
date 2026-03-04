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
    <a href="https://github.com/coco-xyz/clawmark/releases" target="_blank" class="btn-primary">下载扩展 &rarr;</a>
    <a href="https://github.com/coco-xyz/clawmark" target="_blank" class="btn-secondary">查看源码</a>
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

<div class="features-section" id="cm-whats-new">
  <h2 id="cm-wn-title">v0.6 新功能</h2>
  <div id="cm-wn-content" class="features-grid">
    <div class="feature-card">
      <div class="feature-icon">&#128200;</div>
      <h3>控制台</h3>
      <p>完整的配置中心，6 个标签页：概览、账户、连接、分发规则、站点管理和关于。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128274;</div>
      <h3>Google 登录</h3>
      <p>一键 Google OAuth 认证，身份信息自动与标注同步。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128204;</div>
      <h3>标注覆盖层</h3>
      <p>可拖拽、可调整大小的标注窗口，支持分发状态显示和自定义标签。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#127760;</div>
      <h3>站点管理</h3>
      <p>黑名单或白名单模式 — 精确控制 ClawMark 在哪些网站上启用。</p>
    </div>
  </div>
</div>

<div class="quickstart-section">
  <h2>快速开始</h2>

### Chrome 扩展

1. 从 [GitHub Releases](https://github.com/coco-xyz/clawmark/releases) 下载最新版本
2. 打开 `chrome://extensions/`，开启**开发者模式**
3. 点击**加载已解压的扩展程序**，选择扩展文件夹
4. 访问任意网页，开始标注

### 自托管服务端

```bash
git clone https://github.com/coco-xyz/clawmark.git
cd clawmark
npm install
npm start
```

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

      // 更新 What's New 标题
      var wnTitle = document.getElementById('cm-wn-title');
      if (wnTitle) wnTitle.textContent = d.tag_name + ' 新功能';

      // 从 release notes 解析 What's New 区块
      var body = (d.body || '').replace(/\r\n/g, '\n');
      var wnMatch = body.match(/##\s+What's New([\s\S]*?)(?=\n##|$)/);
      if (wnMatch && wnMatch[1].trim()) {
        var wnContent = document.getElementById('cm-wn-content');
        if (wnContent) {
          var sections = wnMatch[1].trim().split(/\n###\s+/).filter(Boolean);
          var html = '';
          // P1-1: XSS escape for content from GitHub API
          function esc(s) { var d = document.createElement('div'); d.textContent = String(s); return d.innerHTML; }
          var icons = {
            'dashboard': '&#128200;', 'welcome': '&#127881;', 'badge': '&#128178;',
            'ux': '&#127912;', 'polish': '&#10024;', 'annotation': '&#128204;',
            'site': '&#127760;', 'sign': '&#128274;', 'auth': '&#128274;',
            'error': '&#9889;', 'fix': '&#128295;', 'perf': '&#9889;',
            'maintenance': '&#128296;', 'default': '&#11088;'
          };
          sections.forEach(function(sec) {
            var lines = sec.split('\n');
            var title = lines[0].trim();
            var shortTitle = title.replace(/^Phase [\d.]+\s*[—\-–]\s*/, '').trim() || title;
            var items = lines.slice(1).filter(function(l){ return l.trim().startsWith('-'); })
              .slice(0, 3)
              .map(function(l){ return l.replace(/^\s*-\s*/, ''); });
            var desc = items.length ? items.join(' · ') : lines.slice(1).filter(Boolean)[0] || '';
            var iconKey = Object.keys(icons).find(function(k){ return title.toLowerCase().includes(k); }) || 'default';
            html += '<div class="feature-card"><div class="feature-icon">' + icons[iconKey] + '</div><h3>' + esc(shortTitle) + '</h3><p>' + esc(desc) + '</p></div>';
          });
          if (html) wnContent.innerHTML = html;
        }
      }

      // 显示最新发布区块
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
      document.getElementById('cm-version').textContent = 'v0.6.3';
    });
})();
</script>
