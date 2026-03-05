---
title: "ClawMark"
description: "Annotate any webpage. Share feedback instantly."
weight: 1
layout: "product"
---

<div class="product-hero">
  <span class="badge" id="cm-badge">Chrome Extension + Embeddable Widget &middot; <span id="cm-version">loading...</span></span>
  <h1>ClawMark</h1>
  <p class="tagline">
    Annotate any webpage. Highlight text, add comments, and route feedback to GitHub Issues, Lark, Telegram, Slack, or email — all in one click.
  </p>
  <div class="hero-actions">
    <a href="https://github.com/coco-xyz/clawmark/releases" target="_blank" class="btn-primary">Download Extension &rarr;</a>
    <a href="https://github.com/coco-xyz/clawmark" target="_blank" class="btn-secondary">View Source</a>
  </div>
</div>

<div class="features-section">
  <h2>Key Features</h2>
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon">&#128269;</div>
      <h3>Browser Extension</h3>
      <p>Chrome Extension (MV3) for in-page text highlighting and annotation. Select text, add thoughts, submit — done.</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128296;</div>
      <h3>Embeddable Widget</h3>
      <p>Drop a single script tag into any site. Collect feedback from visitors without them installing anything.</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128640;</div>
      <h3>Flexible Routing</h3>
      <p>Send annotations to GitHub, Lark, Telegram, Slack, email, Linear, Jira, HxA Connect, or custom webhooks. Rule-based routing with priority control.</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128275;</div>
      <h3>Open Source</h3>
      <p>Self-host the server or use the official hosted service. Full control over your data and integrations.</p>
    </div>
  </div>
</div>

<div class="features-section" id="cm-whats-new">
  <h2 id="cm-wn-title">What's New in v0.6</h2>
  <div id="cm-wn-content" class="features-grid">
    <div class="feature-card">
      <div class="feature-icon">&#128200;</div>
      <h3>Dashboard</h3>
      <p>Full configuration center with 6 tabs — Overview, Account, Connection, Delivery Rules, Site Management, and About.</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128274;</div>
      <h3>Google Sign-In</h3>
      <p>One-click Google OAuth authentication. Your identity syncs with annotations automatically.</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128204;</div>
      <h3>Annotation Overlay</h3>
      <p>Draggable, resizable annotation window with delivery status display and custom tag support.</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#127760;</div>
      <h3>Site Management</h3>
      <p>Blacklist or whitelist mode — control exactly which sites ClawMark is active on.</p>
    </div>
  </div>
</div>

<div class="quickstart-section">
  <h2>Quick Start</h2>

### Install

1. Download the latest release from [GitHub Releases](https://github.com/coco-xyz/clawmark/releases)
2. Open `chrome://extensions/`, enable **Developer Mode**
3. Click **Load unpacked** and select the extension folder
4. Click the ClawMark icon in the toolbar and **Sign in with Google**

### How It Works

Select any text on a webpage — a floating toolbar appears. Click **Comment** or **Issue** to create an annotation. ClawMark automatically routes it to the right place based on your delivery rules.

```
  You annotate         ClawMark Server        Delivery Targets
┌─────────────┐     ┌────────────────┐     ┌──────────────────┐
│  Select text │────▶│ Collect & Store │────▶│ GitHub Issues    │
│  Add comment │     │ Resolve rules  │     │ GitLab Issues    │
│  Submit      │     │ Dispatch       │     │ Lark / Telegram  │
└─────────────┘     └────────────────┘     │ Slack / Email    │
                                            │ Webhook          │
                                            └──────────────────┘
```

### Routing Rules

ClawMark decides where to send each annotation using this priority:

1. **URL pattern rules** — you define patterns like `*github.com/myorg/*` → GitHub Issues
2. **Auto-detect** — on GitHub pages, automatically creates issues in the detected repo
3. **Default target** — your fallback delivery channel
4. **System default** — server-configured catch-all

Manage rules, credentials, and view your annotations in the **Dashboard** (click the extension icon → Open Panel).

### Self-Hosted Server

```bash
git clone https://github.com/coco-xyz/clawmark.git
cd clawmark
npm install
npm start
```

Point the extension to your server: Extension icon → Settings → Connection → enter your server URL.

</div>

<div id="cm-release" class="features-section" style="display:none;">
  <h2>Latest Release</h2>
  <div style="background:var(--tw-prose-pre-bg,#1e1e2e);border-radius:8px;padding:1.5rem;color:var(--tw-prose-body,#cdd6f4);">
    <div style="display:flex;align-items:center;gap:0.75rem;margin-bottom:0.75rem;">
      <strong id="cm-rel-name" style="font-size:1.2rem;"></strong>
      <span id="cm-rel-date" style="opacity:0.6;font-size:0.85rem;"></span>
    </div>
    <div id="cm-rel-body" style="white-space:pre-wrap;font-size:0.9rem;line-height:1.6;max-height:300px;overflow-y:auto;"></div>
    <div style="margin-top:1rem;">
      <a id="cm-rel-link" href="#" target="_blank" style="color:#89b4fa;">View on GitHub &rarr;</a>
    </div>
  </div>
</div>

<div class="bottom-links">
  <a href="https://github.com/coco-xyz/clawmark" target="_blank">GitHub &nearr;</a>
  <a href="https://github.com/coco-xyz/clawmark/releases" target="_blank">Releases &nearr;</a>
  <a href="https://github.com/coco-xyz/clawmark/issues" target="_blank">Issues &nearr;</a>
  <a href="/clawmark/privacy/" target="_blank">Privacy Policy &nearr;</a>
</div>

<script>
(function() {
  fetch('https://api.github.com/repos/coco-xyz/clawmark/releases/latest')
    .then(function(r) { return r.json(); })
    .then(function(d) {
      if (!d.tag_name) return;
      var v = d.tag_name.replace(/^v/, '');

      // Update badge version
      document.getElementById('cm-version').textContent = 'v' + v;

      // Update What's New title
      var wnTitle = document.getElementById('cm-wn-title');
      if (wnTitle) wnTitle.textContent = "What's New in " + d.tag_name;

      // Parse What's New section from release body
      var body = (d.body || '').replace(/\r\n/g, '\n');
      var wnMatch = body.match(/##\s+What's New([\s\S]*?)(?=\n##|$)/);
      if (wnMatch && wnMatch[1].trim()) {
        var wnContent = document.getElementById('cm-wn-content');
        if (wnContent) {
          var sections = wnMatch[1].trim().split(/\n###\s+/).filter(Boolean);
          var html = '';
          // Icon map for common section names
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
            // Extract phase/short name: "Phase 1.5 — Foo" → "Foo", else use title
            var shortTitle = title.replace(/^Phase [\d.]+\s*[—\-–]\s*/, '').trim() || title;
            var items = lines.slice(1).filter(function(l){ return l.trim().startsWith('-'); })
              .slice(0, 3)
              .map(function(l){ return l.replace(/^\s*-\s*/, ''); });
            var desc = items.length ? items.join(' · ') : lines.slice(1).filter(Boolean)[0] || '';
            // Pick icon
            var iconKey = Object.keys(icons).find(function(k){ return title.toLowerCase().includes(k); }) || 'default';
            var icon = icons[iconKey];
            html += '<div class="feature-card"><div class="feature-icon">' + icon + '</div><h3>' + esc(shortTitle) + '</h3><p>' + esc(desc) + '</p></div>';
          });
          if (html) wnContent.innerHTML = html;
        }
      }

      // Show Latest Release section
      var sec = document.getElementById('cm-release');
      if (sec) {
        sec.style.display = '';
        document.getElementById('cm-rel-name').textContent = d.name || d.tag_name;
        document.getElementById('cm-rel-date').textContent = new Date(d.published_at).toLocaleDateString('en-US', {year:'numeric',month:'short',day:'numeric'});
        document.getElementById('cm-rel-body').textContent = body;
        document.getElementById('cm-rel-link').href = d.html_url;
      }
    })
    .catch(function() {
      document.getElementById('cm-version').textContent = 'v0.6.3';
    });
})();
</script>
