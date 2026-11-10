<div align="center">

<a href="https://nelcota.com">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Nelcota/.github/main/profile/logo-dark.svg">
    <img src="https://raw.githubusercontent.com/Nelcota/.github/main/profile/logo-light.svg" alt="Nelcota" width="320">
  </picture>
</a>

# NelcotaJS

**Fine-grained reactivity. Secure by default. Zero browser dependencies.**

[![Repository](https://img.shields.io/badge/Nelcota%2FNelcotaJS-1F2328?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Nelcota/NelcotaJS)
[![npm](https://img.shields.io/npm/v/@nelcota/core?style=for-the-badge&logo=npm&logoColor=white&label=%40nelcota%2Fcore&color=CB3837)](https://www.npmjs.com/package/@nelcota/core)
[![CI](https://img.shields.io/github/actions/workflow/status/Nelcota/NelcotaJS/ci.yml?branch=main&style=for-the-badge&logo=githubactions&logoColor=white&label=CI)](https://github.com/Nelcota/NelcotaJS/actions/workflows/ci.yml)
[![Stars](https://img.shields.io/github/stars/Nelcota/NelcotaJS?style=for-the-badge&logo=githubsponsors&logoColor=white&label=stars&color=E3B341)](https://github.com/Nelcota/NelcotaJS)

</div>

<p align="center">
A reactive frontend framework in TypeScript built on signals.<br>
Components run once, and only the DOM nodes bound to a signal update.<br>
<b>Safe output by default, web standards only, and core + dom under 9 kB gzip.</b>
</p>

> [!WARNING]
> **Pre-alpha.** Client-side rendering only, with SSR and islands planned. Early releases are on npm and the API may still change.

## Why NelcotaJS

<table>
<tr>
<td width="33%" valign="top">

### ⚡ Signals, not re-renders

Components run once. `{count()}` compiles to a binding, so a change touches only that text node.

</td>
<td width="33%" valign="top">

### 🛡️ Safe by default

Escaped output, blocked `javascript:` URLs, strict CSP and Trusted Types. Raw HTML only through `unsafeHTML`.

</td>
<td width="33%" valign="top">

### 🧩 Just TSX

Full editor support, no custom language server, and source maps back to your code.

</td>
</tr>
<tr>
<td width="33%" valign="top">

### 🪶 Tiny by budget

`core` + `dom` stay under **9 kB gzip**, enforced in CI. Optional features are measured on their own.

</td>
<td width="33%" valign="top">

### ⏳ Async built in

Async computeds and `isPending` handle loading, failure, retry and cancellation.

</td>
<td width="33%" valign="top">

### 🌐 Web standards only

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

| Package | What it does |
| --- | --- |
| [`@nelcota/core`](https://github.com/Nelcota/NelcotaJS/tree/main/packages/core) | Signals, computeds, effects, `batch`, `untrack`, roots, context and `catchError`. Async computeds live in `@nelcota/core/async`. |
| [`@nelcota/dom`](https://github.com/Nelcota/NelcotaJS/tree/main/packages/dom) | Renderer, JSX runtime, `For`, `Show`, `spread` and `unsafeHTML`, plus optional context, error boundary and loading entries. |
| [`@nelcota/compiler`](https://github.com/Nelcota/NelcotaJS/tree/main/packages/compiler) | TSX to cloned templates and fine-grained bindings with source maps, built on Oxc. |
| [`vite-plugin-nelcota`](https://github.com/Nelcota/NelcotaJS/tree/main/packages/vite-plugin-nelcota) | Vite integration with HMR and source maps. |

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white) ![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white) ![Bun](https://img.shields.io/badge/Bun-000000?style=flat-square&logo=bun&logoColor=white) ![Oxc](https://img.shields.io/badge/Oxc-1F2328?style=flat-square)

## Learn more

- **Guides:** [Async computations and loading](https://github.com/Nelcota/NelcotaJS/blob/main/docs/guides/async-computations.md) · [Debugging, context and recovery](https://github.com/Nelcota/NelcotaJS/blob/main/docs/guides/developer-foundations.md) · [Benchmarks](https://github.com/Nelcota/NelcotaJS/blob/main/docs/guides/benchmarks.md)
- **Design:** [Signals RFC](https://github.com/Nelcota/NelcotaJS/blob/main/docs/rfcs/0001-signals.md) · [Async computations RFC](https://github.com/Nelcota/NelcotaJS/blob/main/docs/rfcs/0003-async-computations.md) · [Router RFC](https://github.com/Nelcota/NelcotaJS/blob/main/docs/rfcs/0004-router.md)
- **Project:** [Roadmap](https://github.com/Nelcota/NelcotaJS/blob/main/docs/project/roadmap.md) · [Decisions](https://github.com/Nelcota/NelcotaJS/blob/main/docs/project/decisions.md)

## Contribute

Read the [contributing guide](https://github.com/Nelcota/NelcotaJS/blob/main/CONTRIBUTING.md) and open an issue or pull request on [NelcotaJS](https://github.com/Nelcota/NelcotaJS). Questions go through the [support guide](https://github.com/Nelcota/.github/blob/main/SUPPORT.md), and everyone follows the [code of conduct](https://github.com/Nelcota/.github/blob/main/CODE_OF_CONDUCT.md).

Found a vulnerability? Report it privately through **GitHub Security Advisories**, as described in the [security policy](https://github.com/Nelcota/NelcotaJS/blob/main/SECURITY.md).

<div align="center">
<br>
<sub>Also from Nelcota: <a href="https://github.com/Nelcota/Nelcota">Nelcota</a> (Postgres backend) · <a href="https://github.com/Nelcota/NelcotaDeploy">NelcotaDeploy</a> · <a href="https://github.com/Nelcota/NelcotaScreenShare">NelcotaScreenShare</a> · <a href="https://github.com/Nelcota/NelcotaPrompts">NelcotaPrompts</a></sub><br>
<sub><a href="https://nelcota.com">nelcota.com</a> · MIT licensed</sub>
</div>
