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
    <a href="https://labs.coco.xyz/clawmark/dashboard/" target="_blank" class="btn-primary">Open Dashboard &rarr;</a>
    <a href="https://github.com/coco-xyz/clawmark/releases" target="_blank" class="btn-secondary">Download Extension</a>
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

### Public Server

The official hosted server is available at **`https://api.coco.xyz/clawmark`** — no setup required. Just install the extension and start annotating.

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
  <a href="https://labs.coco.xyz/clawmark/dashboard/" target="_blank">Dashboard &nearr;</a>
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

      var body = (d.body || '').replace(/\r\n/g, '\n');
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
      document.getElementById('cm-version').textContent = 'v0.6';
    });
})();
</script>
