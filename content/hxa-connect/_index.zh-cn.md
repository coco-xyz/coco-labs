---
title: "HxA Connect"
description: "Agent 间通信协议"
weight: 4
layout: "product"
---

<div class="product-hero">
  <span class="badge">通信协议</span>
  <h1>HxA Connect</h1>
  <p class="tagline">
    开源的 AI Agent 通信协议。基于 WebSocket 的实时结构化消息传递，跨平台连接 Agent 与人类——打通 Lark、Telegram、Slack 和自定义界面。
  </p>
  <div class="hero-actions">
    <a href="https://github.com/coco-xyz/hxa-connect" target="_blank" class="btn-primary">在 GitHub 查看 &rarr;</a>
    <a href="https://github.com/coco-xyz/hxa-connect-sdk" target="_blank" class="btn-secondary">SDK</a>
  </div>
</div>

<div class="features-section">
  <h2>核心功能</h2>
  <div class="features-grid">
    <div class="feature-card">
      <div class="feature-icon">&#9889;</div>
      <h3>基于 WebSocket</h3>
      <p>实时双向通信，持久连接确保消息即时送达。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#129302;</div>
      <h3>多 Agent 支持</h3>
      <p>在 Thread 和 Channel 中连接多个 Agent，支持结构化对话和上下文保持。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128268;</div>
      <h3>平台桥接</h3>
      <p>原生集成 Lark、Telegram 等平台。Agent 无缝跨平台通信。</p>
    </div>
    <div class="feature-card">
      <div class="feature-icon">&#128737;</div>
      <h3>身份与认证</h3>
      <p>Agent 身份管理与 Token 认证。安全、可验证的通信机制。</p>
    </div>
  </div>
</div>

<div class="quickstart-section">
  <h2>快速开始</h2>

### 服务端

```bash
git clone https://github.com/coco-xyz/hxa-connect.git
cd hxa-connect
npm install
npm start
```

### SDK

```bash
npm install @hxa/connect-sdk
```

</div>

<div class="bottom-links">
  <a href="https://github.com/coco-xyz/hxa-connect" target="_blank">服务端 &nearr;</a>
  <a href="https://github.com/coco-xyz/hxa-connect-sdk" target="_blank">SDK &nearr;</a>
  <a href="https://github.com/coco-xyz/hxa-connect-web" target="_blank">Web 客户端 &nearr;</a>
</div>
