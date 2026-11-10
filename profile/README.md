<a href="https://nelcota.com">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Nelcota/.github/main/profile/banner-dark.svg">
    <img src="https://raw.githubusercontent.com/Nelcota/.github/main/profile/banner-light.svg" alt="Nelcota: own the whole stack. Data, deploy, interface and team tools in one open-source ecosystem." width="100%">
  </picture>
</a>

<div align="center">

[![nelcota.com](https://img.shields.io/badge/nelcota.com-1F2328?style=for-the-badge&logo=data:image/svg%2Bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI%2BPHBhdGggZmlsbD0iI0VBNDMzNSIgZD0iTTEyIDEyTDIuNDc0IDYuNUExMSAxMSAwIDAgMSAyMS41MjYgNi41WiIvPjxwYXRoIGZpbGw9IiNGQkJDMDQiIGQ9Ik0xMiAxMkwyMS41MjYgNi41QTExIDExIDAgMCAxIDEyIDIzWiIvPjxwYXRoIGZpbGw9IiMzNEE4NTMiIGQ9Ik0xMiAxMkwxMiAyM0ExMSAxMSAwIDAgMSAyLjQ3NCA2LjVaIi8%2BPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNS4yIiBmaWxsPSIjZmZmIi8%2BPGNpcmNsZSBjeD0iMTIiIGN5PSIxMiIgcj0iNC4xIiBmaWxsPSIjNDI4NUY0Ii8%2BPC9zdmc%2BCg%3D%3D)](https://nelcota.com)
[![Docs](https://img.shields.io/badge/docs-F97316?style=for-the-badge&logo=gitbook&logoColor=white)](https://nelcota.com/docs/)
[![Release](https://img.shields.io/github/v/release/Nelcota/Nelcota?style=for-the-badge&logo=github&logoColor=white&label=release&color=2EA043)](https://github.com/Nelcota/Nelcota/releases)
[![Stars](https://img.shields.io/github/stars/Nelcota/Nelcota?style=for-the-badge&logo=githubsponsors&logoColor=white&label=stars&color=E3B341)](https://github.com/Nelcota/Nelcota)

</div>

<h3 align="center">Stop renting your infrastructure. Run all of it yourself.</h3>

<p align="center">
Nelcota is an open-source ecosystem for building and running software end to end:<br>
the database and API, the deploy pipeline, the frontend framework and the tools your team uses every day.<br>
<b>Every piece is self-hosted, so the stack, the data and the bill stay yours.</b>
</p>

<br>

## The stack

<table>
<tr>
<td width="50%" valign="top">

### 🐘 Data &amp; API
**[Nelcota](https://github.com/Nelcota/Nelcota)**

Your PostgreSQL schema becomes a complete backend: REST API, auth, file storage, webhooks and an admin panel, in a single Rust binary. Row-level security decides what every request can do.

![Rust](https://img.shields.io/badge/Rust-CE422B?style=flat-square&logo=rust&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL_17-4169E1?style=flat-square&logo=postgresql&logoColor=white)

</td>
<td width="50%" valign="top">

### 🚀 Deploy
**[NelcotaDeploy](https://github.com/Nelcota/NelcotaDeploy)**

Push to GitHub, get a running container with HTTPS, logs, metrics, uptime checks, previews, databases and automatic rollback. One VPS or many over SSH.

![Bun](https://img.shields.io/badge/Bun-000000?style=flat-square&logo=bun&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Traefik](https://img.shields.io/badge/Traefik-24A1C1?style=flat-square&logo=traefikproxy&logoColor=white)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ⚛️ Interface
**[NelcotaJS](https://github.com/Nelcota/NelcotaJS)** <sup>pre-alpha</sup>

A reactive frontend framework built on signals: components run once and only the bound DOM nodes update. Secure by default and under 9 kB gzip.

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white)

</td>
<td width="50%" valign="top">

### 👥 Team
**[NelcotaScreenShare](https://github.com/Nelcota/NelcotaScreenShare)** · **[NelcotaPrompts](https://github.com/Nelcota/NelcotaPrompts)**

Screen sharing with audio and chat, and a private prompt library with variables, version history and full-text search. Tools your team owns instead of subscribes to.

![LiveKit](https://img.shields.io/badge/LiveKit-1F2328?style=flat-square&logo=webrtc&logoColor=white) ![React Router](https://img.shields.io/badge/React_Router-CA4245?style=flat-square&logo=reactrouter&logoColor=white)

</td>
</tr>
</table>

**SDKs:** [`@nelcota/client`](https://github.com/Nelcota/Nelcota/tree/main/sdk/typescript) · [`@nelcota/nextjs`](https://github.com/Nelcota/Nelcota/tree/main/sdk/nextjs) · [`@nelcota/ssr`](https://github.com/Nelcota/Nelcota/tree/main/sdk/ssr) · [`nelcota-client`](https://github.com/Nelcota/Nelcota/tree/main/sdk/rust) for Rust<br>
**Website:** [NelcotaWebsite](https://github.com/Nelcota/NelcotaWebsite), the site and docs in English and Portuguese, built with Astro.

## Try it

```sh
curl -fsSL https://raw.githubusercontent.com/Nelcota/Nelcota/main/scripts/install.sh | NELCOTA_SKIP_DOCKER=1 sh
mkdir my-app && cd my-app
nelcota dev   # PostgreSQL, the API and the admin panel, running locally
```

Write your tables in SQL, run `nelcota migrate` and the API is live. The [quickstart](https://github.com/Nelcota/Nelcota/blob/main/docs/quickstart.md) takes it from there, and the [self-hosting guide](https://github.com/Nelcota/Nelcota/blob/main/docs/deploy.md) puts it in production.

## Why Nelcota

| | |
| --- | --- |
| 🏠 **Yours to run** | Everything runs on a server you control, from a single VPS up. |
| 🧱 **Built on standards** | PostgreSQL, SQL, Docker and web standards instead of proprietary layers. |
| ⚡ **Small and fast** | Single binaries, few moving parts, size and performance budgets enforced in CI. |
| 🛡️ **Secure by default** | Safe defaults out of the box, and the unsafe path is always explicit. |
| 🔓 **No lock-in** | Your data and code stay portable, and [leaving is documented](https://github.com/Nelcota/Nelcota/blob/main/docs/leaving.md). |

## Contribute

Pick a project, read the [contributing guide](https://github.com/Nelcota/.github/blob/main/CONTRIBUTING.md) and open an issue or pull request. Questions go through the [support guide](https://github.com/Nelcota/.github/blob/main/SUPPORT.md), and everyone follows the [code of conduct](https://github.com/Nelcota/.github/blob/main/CODE_OF_CONDUCT.md).

Found a vulnerability? Report it privately through **GitHub Security Advisories** in the affected repository, as described in the [security policy](https://github.com/Nelcota/.github/blob/main/SECURITY.md).

<div align="center">
<br>
<sub><a href="https://nelcota.com">nelcota.com</a> · open source, self-hosted, yours</sub>
</div>
