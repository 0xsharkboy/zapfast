---
layout: home
title: ZapFast
description: A native WhatsApp client for Linux, macOS, and Windows, written in Rust.
permalink: /
hero:
  name: ZapFast
  text: WhatsApp, native and fast
  tagline: A small WhatsApp client for chats, voice messages, attachments, and notifications on Linux, macOS, and Windows.
  actions:
    - theme: brand
      text: Download
      link: /download/
    - theme: alt
      text: See the benchmarks
      link: /benchmarks/
    - theme: alt
      text: GitHub
      link: https://github.com/crmne/zapfast
  image:
    src: /screenshot.png
    alt: "ZapFast showing a chat with a photo, a document, a voice message, a quoted reply, and a link preview"
    width: 1387
    height: 1040

features:
  - icon: ⚡
    title: About 87% less idle RAM
    details: In our Linux test, ZapFast used 150 MB versus 1.13 GB for WhatsApp Web and its Chromium processes. Native Rust, with no browser engine.
    link: /benchmarks/
    link_text: See how we measured it
  - icon: 🎤
    title: Voice messages
    details: Play, seek, and record voice messages in the chat. OGG/Opus support is built in.
  - icon: 🖼️
    title: Attachments
    details: Photos, GIFs, stickers, documents, polls, locations, and link previews appear in the chat. Add captions before sending files.
  - icon: 🔔
    title: Background mode
    details: Closing the window keeps ZapFast linked in the tray. Notifications show the chat picture, and muted chats stay quiet.
  - icon: ⌨️
    title: Keyboard shortcuts
    details: Search, switch chats, reply, and record with shortcuts. Select and copy text, including across messages.
  - icon: 🔓
    title: Open source
    details: MIT-licensed Rust built with egui and whatsapp-rust. The linking process is documented.
    link: https://github.com/crmne/zapfast
    link_text: Read the source
---

## A quick tour

Search and switch chats with shortcuts, right-click to reply, browse GIFs and
stickers, and change themes. This silent demo uses sample conversations.

<video class="zapfast-showcase" controls muted playsinline preload="none" poster="/assets/images/launch-demo-poster.png" aria-label="A 41-second tour of ZapFast with sample chats and keyboard shortcut captions">
  <source src="/assets/videos/launch-demo.mp4" type="video/mp4">
</video>

## Measured on a real Linux desktop

![Idle RAM: ZapFast 150 MB, WhatsApp Web and Chromium 1.13 GB. Four paired Linux runs, measured with PSS.](/assets/benchmarks/2026-09-15/memory.svg)

The first window appeared in **152 ms for ZapFast versus 528 ms for Chromium**.
We also observed the chat UI at **about 0.7 s versus 4.1 s**, with different
detectors for the native and web interfaces. These are medians from four
paired launches on one Linux machine, with warm caches and the same account.

[Read the benchmark, including the chat-display method and raw results →](/benchmarks/)

<style>
  .zapfast-showcase {
    display: block;
    width: 100%;
    height: auto;
    border-radius: 12px;
    box-shadow: 0 12px 48px rgba(0, 0, 0, 0.35);
  }
  /* Override the square hero slot to fit the screenshot. */
  .VPHero .image-container {
    width: 100% !important;
    height: auto !important;
    transform: none !important;
  }
  .VPHero .image-src {
    position: relative !important;
    top: auto !important;
    left: auto !important;
    transform: none !important;
    width: 100% !important;
    height: auto !important;
    max-width: 100% !important;
    max-height: none !important;
    padding: 0 !important;
    border-radius: 12px;
    box-shadow: 0 12px 48px rgba(0, 0, 0, 0.45);
  }
  @media (max-width: 959px) {
    .VPHero .image {
      margin: 0 0 24px !important;
    }
  }
</style>
