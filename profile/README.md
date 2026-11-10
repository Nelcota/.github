<div align="center">

<a href="https://nelcota.com">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Nelcota/.github/main/profile/logo-dark.svg">
    <img src="https://raw.githubusercontent.com/Nelcota/.github/main/profile/logo-light.svg" alt="Nelcota" width="320">
  </picture>
</a>

# NelcotaJS

**Fine-grained reactivity. Secure by default. Zero browser dependencies.**

A reactive frontend framework in TypeScript built on signals.<br>
Components run once, and only the DOM nodes bound to a signal update.

[![npm](https://img.shields.io/npm/v/@nelcota/core?style=for-the-badge&logo=npm&logoColor=white&label=npm&color=CB3837)](https://www.npmjs.com/package/@nelcota/core)
[![CI](https://img.shields.io/github/actions/workflow/status/Nelcota/NelcotaJS/ci.yml?branch=main&style=for-the-badge&logo=githubactions&logoColor=white&label=CI)](https://github.com/Nelcota/NelcotaJS/actions/workflows/ci.yml)
[![Size](https://img.shields.io/badge/core_%2B_dom-%E2%89%A4_9_kB_gzip-15803D?style=for-the-badge)](https://github.com/Nelcota/NelcotaJS/blob/main/.size-limit.json)
[![License](https://img.shields.io/badge/license-MIT-1F6FEB?style=for-the-badge)](https://github.com/Nelcota/NelcotaJS/blob/main/LICENSE)
[![Stars](https://img.shields.io/github/stars/Nelcota/NelcotaJS?style=for-the-badge&logo=github&logoColor=white&label=stars&color=E3B341)](https://github.com/Nelcota/NelcotaJS)

<sub>⚠️ <b>Pre-alpha</b> · client-side rendering only, SSR and islands planned · the API may still change</sub>

</div>

## Why NelcotaJS

<table>
<tr>
<td width="33%" valign="top">

#### ⚡ Signals, not re-renders

Components run once. `{count()}` compiles to a binding, so a change touches only that text node.

#### 🪶 Tiny by budget

`core` + `dom` stay under 9 kB gzip, enforced in CI. Optional features are measured on their own.

</td>
<td width="33%" valign="top">

#### 🛡️ Safe by default

Escaped output, blocked `javascript:` URLs, strict CSP and Trusted Types. Raw HTML only through `unsafeHTML`.

#### ⏳ Async built in

Async computeds and `isPending` handle loading, failure, retry and cancellation.

</td>
<td width="33%" valign="top">

#### 🧩 Just TSX

Full editor support, no custom language server, and source maps back to your code.

#### 🌐 Web standards only

No third-party code shipped to the browser. Just the platform and your app.

</td>
</tr>
</table>

## A taste

```tsx
import { computed, signal } from "@nelcota/core";
import { render } from "@nelcota/dom";

function Counter() {
  const count = signal(0);
  const double = computed(() => count() * 2);

  return (
    <button type="button" onClick={() => count.set(count() + 1)}>
      Clicks: {count()} (double: {double()})
    </button>
  );
}

render(() => <Counter />, document.getElementById("app")!);
```

## Get started

```sh
bun add @nelcota/core @nelcota/dom
bun add -d vite-plugin-nelcota
```

```ts
// vite.config.ts
import { defineConfig } from "vite";
import nelcota from "vite-plugin-nelcota";

export default defineConfig({ plugins: [nelcota()] });
```

The [examples](https://github.com/Nelcota/NelcotaJS/tree/main/examples) cover a counter, a todo list, async data and a full-stack dashboard.

## Packages

<table>
<tr>
<td width="50%" valign="top">

#### 🧠 [@nelcota/core](https://github.com/Nelcota/NelcotaJS/tree/main/packages/core) &nbsp;[![npm](https://img.shields.io/npm/v/@nelcota/core?style=flat-square&color=CB3837&label=)](https://www.npmjs.com/package/@nelcota/core)

The reactive engine: signals, computeds, effects, `batch`, `untrack`, roots and context. Async computeds live in `@nelcota/core/async`.

#### ⚙️ [@nelcota/compiler](https://github.com/Nelcota/NelcotaJS/tree/main/packages/compiler) &nbsp;[![npm](https://img.shields.io/npm/v/@nelcota/compiler?style=flat-square&color=CB3837&label=)](https://www.npmjs.com/package/@nelcota/compiler)

Turns TSX into cloned templates and fine-grained bindings, with source maps. Built on Oxc.

</td>
<td width="50%" valign="top">

#### 🖼️ [@nelcota/dom](https://github.com/Nelcota/NelcotaJS/tree/main/packages/dom) &nbsp;[![npm](https://img.shields.io/npm/v/@nelcota/dom?style=flat-square&color=CB3837&label=)](https://www.npmjs.com/package/@nelcota/dom)

Renderer and JSX runtime with `For`, `Show` and `spread`, plus optional context, error boundary and loading entries.

#### 🔌 [vite-plugin-nelcota](https://github.com/Nelcota/NelcotaJS/tree/main/packages/vite-plugin-nelcota) &nbsp;[![npm](https://img.shields.io/npm/v/vite-plugin-nelcota?style=flat-square&color=CB3837&label=)](https://www.npmjs.com/package/vite-plugin-nelcota)

Drop-in Vite integration with HMR and source maps. One line in `vite.config.ts`.

</td>
</tr>
</table>

**Built with** &nbsp;![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white) ![Bun](https://img.shields.io/badge/Bun-000000?style=flat-square&logo=bun&logoColor=white) ![Oxc](https://img.shields.io/badge/Oxc-1F2328?style=flat-square)

## Learn more

<table>
<tr>
<td width="33%" valign="top">

#### 📘 Guides

Hands-on walkthroughs for everyday work.

- [Async computations and loading](https://github.com/Nelcota/NelcotaJS/blob/main/docs/guides/async-computations.md)
- [Debugging, context and recovery](https://github.com/Nelcota/NelcotaJS/blob/main/docs/guides/developer-foundations.md)
- [Benchmarks](https://github.com/Nelcota/NelcotaJS/blob/main/docs/guides/benchmarks.md)

</td>
<td width="33%" valign="top">

#### 📐 Design

The reasoning behind each core decision.

- [Signals RFC](https://github.com/Nelcota/NelcotaJS/blob/main/docs/rfcs/0001-signals.md)
- [Async computations RFC](https://github.com/Nelcota/NelcotaJS/blob/main/docs/rfcs/0003-async-computations.md)
- [Router RFC](https://github.com/Nelcota/NelcotaJS/blob/main/docs/rfcs/0004-router.md)

</td>
<td width="33%" valign="top">

#### 🗺️ Project

Where NelcotaJS is today and where it is going.

- [Roadmap](https://github.com/Nelcota/NelcotaJS/blob/main/docs/project/roadmap.md)
- [Decisions](https://github.com/Nelcota/NelcotaJS/blob/main/docs/project/decisions.md)
- [Examples](https://github.com/Nelcota/NelcotaJS/tree/main/examples)

</td>
</tr>
</table>

## Contribute

Issues and pull requests are welcome on [NelcotaJS](https://github.com/Nelcota/NelcotaJS). Start here:

[![Contributing guide](https://img.shields.io/badge/Contributing_guide-2EA043?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nelcota/NelcotaJS/blob/main/CONTRIBUTING.md)
[![Open an issue](https://img.shields.io/badge/Open_an_issue-1F2328?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nelcota/NelcotaJS/issues)
[![Support](https://img.shields.io/badge/Support-1F6FEB?style=for-the-badge&logo=githubsponsors&logoColor=white)](https://github.com/Nelcota/.github/blob/main/SUPPORT.md)
[![Code of conduct](https://img.shields.io/badge/Code_of_conduct-8250DF?style=for-the-badge&logo=handshake&logoColor=white)](https://github.com/Nelcota/.github/blob/main/CODE_OF_CONDUCT.md)

> [!IMPORTANT]
> **Found a vulnerability?** Don't open a public issue. Report it privately through GitHub Security Advisories, as described in the [security policy](https://github.com/Nelcota/NelcotaJS/blob/main/SECURITY.md).

---

<div align="center">

**Also from Nelcota**

[![Nelcota](https://img.shields.io/badge/Nelcota-Postgres_backend-CE422B?style=flat-square)](https://github.com/Nelcota/Nelcota)
[![NelcotaDeploy](https://img.shields.io/badge/NelcotaDeploy-Self--hosted_deploys-2496ED?style=flat-square)](https://github.com/Nelcota/NelcotaDeploy)
[![NelcotaScreenShare](https://img.shields.io/badge/NelcotaScreenShare-Screen_sharing-24A1C1?style=flat-square)](https://github.com/Nelcota/NelcotaScreenShare)
[![NelcotaPrompts](https://img.shields.io/badge/NelcotaPrompts-Prompt_library-CA4245?style=flat-square)](https://github.com/Nelcota/NelcotaPrompts)

<sub><a href="https://nelcota.com">nelcota.com</a> · NelcotaJS is MIT licensed</sub>

</div>
