<!--
  This README is rendered on the xGoose-dev organization profile page on
  GitHub. It lives at .github/profile/README.md by convention.

  Keep the design in sync with xgoose.org:
    • brand gradient = indigo (#6366f1) → violet (#a855f7) → pink (#ec4899)
    • compact hero, repo map, install table, "built on Cloudflare" footer
  Anything that requires JS or custom CSS will not render here — keep it
  to plain markdown + inline HTML + shields.io badges.
-->

<div align="center">

<img src="https://xgoose.org/logo.png" alt="xgoose" width="160" />

<h1>xgoose</h1>

<p><strong>An AI agent that lives in your browser.</strong></p>

<p>
  Floating chat panel for Chrome, Firefox, and Safari.<br/>
  Site-aware <em>skills</em> let it search, reason, and act on whatever page
  you're on — powered by a free, built-in AI gateway.
</p>

<p>
  <a href="https://xgoose.org">
    <img alt="xgoose.org" src="https://img.shields.io/badge/site-xgoose.org-6366F1?style=for-the-badge&labelColor=0a0a14" />
  </a>
  <a href="https://xgoose.org/skills/">
    <img alt="Skill registry" src="https://img.shields.io/badge/skills-registry-A855F7?style=for-the-badge&labelColor=0a0a14" />
  </a>
  <a href="https://xgoose.org/docs/">
    <img alt="Docs" src="https://img.shields.io/badge/docs-quickstart-EC4899?style=for-the-badge&labelColor=0a0a14" />
  </a>
</p>

<p>
  <a href="https://xgoose.org">
    <img alt="status" src="https://img.shields.io/badge/status-live-22C55E?labelColor=0a0a14" />
  </a>
  <a href="https://workers.cloudflare.com">
    <img alt="cloudflare" src="https://img.shields.io/badge/runs%20on-Cloudflare-F38020?logo=cloudflare&logoColor=white&labelColor=0a0a14" />
  </a>
  <a href="https://nextjs.org">
    <img alt="next.js" src="https://img.shields.io/badge/Next.js-15-black?logo=next.js&labelColor=0a0a14" />
  </a>
  <a href="#license">
    <img alt="license" src="https://img.shields.io/badge/license-MIT--friendly-6366F1?labelColor=0a0a14" />
  </a>
</p>

</div>

---

## What is xgoose?

A pocket-sized AI agent that sits next to whatever website you're on. A small
floating button opens a chat panel; the agent reads the page, follows
**skills** (tiny JS programs that teach it how to use a site), and runs JS in
the page on your behalf.

- **Zero-config AI** — a free built-in gateway means there's nothing to set up.
- **Bring your own key** — paste an OpenAI / Anthropic / Gemini / OpenRouter
  key if you'd rather.
- **One-click skills** — install community skills straight from
  [xgoose.org/skills](https://xgoose.org/skills/).
- **Open source** — Chrome, Firefox, and Safari (iOS + macOS) hosts all share
  the same agent core.

---

## Repositories

| Repo | What it is |
| --- | --- |
| [`xgoose-web`](https://github.com/xGoose-dev/xgoose-web) | Marketing site, skill registry, free AI gateway. Next.js 15 + Cloudflare Workers + D1. |
| [`xgoose-agent-core`](https://github.com/xGoose-dev/xgoose-agent-core) | Headless agent loop, tools, system prompt, pricing — the brain shared by every host. |
| [`xgoose-skills`](https://github.com/xGoose-dev/xgoose-skills) | First-party skills (aa-awards, flyertalk, uscardforum, …) published to the registry. |
| [`xgoose-extension-chrome`](https://github.com/xGoose-dev/xgoose-extension-chrome) | Chrome MV3 host. |
| [`xgoose-extension-firefox`](https://github.com/xGoose-dev/xgoose-extension-firefox) | Firefox MV3 host (desktop + Android). |
| [`xgoose-extension-safari`](https://github.com/xGoose-dev/xgoose-extension-safari) | Safari WebExtension for iOS + macOS. |

---

## Install

| Browser | Where |
| --- | --- |
| Chrome | [Chrome Web Store →](https://xgoose.org) |
| Firefox | [Firefox Add-ons →](https://xgoose.org) |
| Safari (macOS + iOS) | [App Store →](https://xgoose.org) |
| Any site (embed) | `<script src="https://xgoose.org/embed.js">` |

Already installed? **[Browse community skills →](https://xgoose.org/skills/)**

---

## Architecture at a glance

```
        ┌─────────────────────────────────────────────────┐
        │  Browser host (Chrome / Firefox / Safari)       │
        │  ┌──────────────┐   ┌────────────────────────┐  │
        │  │ Floating UI  │ ↔ │ @xgoose/agent-core     │  │
        │  └──────────────┘   │  • tool loop           │  │
        │                     │  • skill runtime       │  │
        │                     │  • page controller     │  │
        │                     └───────────┬────────────┘  │
        └──────────────────────────────────┼──────────────┘
                                           │
                                           ▼
                       ┌───────────────────────────────────┐
                       │  api.xgoose.org   (Cloudflare)    │
                       │  • free AI gateway                │
                       │  • skill registry (D1)            │
                       │  • accounts + device flow         │
                       └───────────────────────────────────┘
```

Everything outside the browser runs on the Cloudflare edge: **Workers** for
the API, **D1** for the skill registry and accounts, **Pages** for the
marketing site, **Email Routing** for sign-in. Zero containers, zero
cold-start surprises.

---

## License

Source is published per-repo; the agent core, skills, and extensions are
**MIT-friendly**. The xgoose.org service is hosted by the maintainers and
free to use within fair-use limits.

---

<div align="center">
<sub>Made with <strong>✦</strong> by the xgoose team. Floating button, big ambitions.</sub>
</div>
