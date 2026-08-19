> **Community hub.** Star this repository, open issues, and follow the changelog. Component source is **not** stored here — install with `npx base-ui-cli add button` from [base-ui.net](https://base-ui.net).

# Base UI — Angular + Tailwind Component Library

A comprehensive Tailwind CSS component ecosystem for modern Angular: **208 components and blocks** (119 free, 89 pro), **390 icons**, and 17 full page layouts — standalone, zoneless, signal-based and **SSR-safe**, delivered shadcn-style: the source is copied into your project and it's yours.

📚 **Documentation & live previews**: [base-ui.net](https://base-ui.net)  
📝 **Changelog**: [base-ui.net/changelog](https://base-ui.net/changelog) · [CHANGELOG.md](CHANGELOG.md) · [Issues](https://github.com/Base-ui-ng/base-ui/issues)  
♿ **Accessibility (ACR)**: [base-ui.net/accessibility](https://base-ui.net/accessibility) · `npm run test:a11y`  
🖥️ **SSR-safe**: the docs site prerenders every catalog route, enforced by a blocking CI job · [how we verify it](https://base-ui.net/learn/angular-ssr-safe-component-library/)  
🤖 **AI agents (MCP)**: [base-ui.net/getting-started#ai-agents-mcp](https://base-ui.net/getting-started#ai-agents-mcp) · `@lussos/base-ui-mcp`  
🎨 **Figma Design System**: [Figma Community File](https://www.figma.com/community/file/1662825988518656661)  
✨ **See what you can build for free**: [Live Admin Dashboard Demo](https://base-ui-free-dashboard-demo.pages.dev/app/dashboard) (Source code: [base-ui-free-dashboard](https://github.com/lussos/base-ui-free-dashboard))

---

## 🚀 Quick Start (Free Tier)

The free tier is production-ready with no account or license: **all primitives** (buttons, cards, dialogs, hover cards, menubars, inputs, currency fields, selects, tabs, toasts, tooltips, and more) plus **all 19 form blocks** (login, signup, checkout, billing, wizard, …).

### 1. Initialize your project

```bash
npx base-ui-cli init
```

This writes `base-ui.json`, creates `base-ui.css` (CDK overlay styles, keyframes, autofill fixes) imported from your global stylesheet, and downloads the icon sprites into your assets folder. Use `--yes` to accept defaults non-interactively.

### 2. Configure Tailwind CSS

Base UI works with **standard Tailwind CSS 4** — no custom theme file required.

1. Install Tailwind CSS 4 and PostCSS ([installation guide](https://tailwindcss.com/docs/installation)).
2. Create `src/tailwind.css`, register it in `angular.json` **before** global SCSS, and point `@source` at your templates:

```css
@import "tailwindcss";

@source "./src/**/*.{html,ts}";
```

Components use standard Tailwind spacing (e.g. `p-4`) and standard colors (`blue-500` for `color="primary"`).

**Optional — custom brand color:** override Tailwind's blue scale in `:root`:

```css
:root {
  --color-blue-500: rgb(139 92 246); /* e.g. violet instead of blue */
}
```

Use the demo app's theme customizer to export a full 50–950 scale. Brand, radius, background, font, and density persist in the demo (`localStorage`) and can be shared with `?theme=violet&radius=0.75&bg=zinc&font=inter&density=compact`.

### 3. Add components

```bash
npx base-ui-cli add button card dialog
```

Component dependencies are resolved recursively, and missing npm packages are installed with your package manager automatically. Run `npx base-ui-cli list` to see everything that's available.

Later, `npx base-ui-cli diff` shows what's changed upstream for components you've already installed, and `npx base-ui-cli update` pulls those changes in — automatically for files you haven't touched, interactively (keep / take upstream / save side-by-side) for anything you've customized that also changed upstream. See [`base-ui-cli`](https://www.npmjs.com/package/base-ui-cli) for details.

### 4. Import in your Angular app

All components are **standalone** — import them from your local components folder:

```typescript
// app.component.ts (standalone)
import { CardComponent } from './components/card/card.component';
import { BaseButtonDirective } from './components/button/button.directive';

@Component({
  selector: 'app-root',
  standalone: true,
  imports: [CardComponent, BaseButtonDirective],
  template: `...`,
})
export class AppComponent {}
```

---

## 💎 Base UI Pro

Pro components are the pre-built blocks — blog and article cards, ecommerce blocks, media and social widgets, 15 full page layouts — plus advanced widgets (data table, date pickers, command palette, mega menu, file upload, multi-select, rich text editor, crop image, product gallery, tree, mention input, splitter).

After purchasing a license at [base-ui.net](https://base-ui.net), set your license key once and add pro components with the same CLI:

```bash
export BASE_UI_LICENSE_KEY=your-license-key
npx base-ui-cli add layout-dashboard blog-card-gradient-hero
```

The key is validated server-side by the pro registry on every fetch. In CI, set `BASE_UI_LICENSE_KEY` as a secret.

---

## 🛍️ Templates

Templates are complete, production-grade applications built on Pro — every route wired up, shipped as source you own. Each bundle includes a Base UI Pro license.

- **[Motif](https://base-ui.net/templates/motif)** — an Angular 22 + Tailwind commerce storefront: mega menu, category listing, product detail, cart, checkout, order tracking and an editorial journal. **$149** including Pro. [Live demo](https://commerce-template.base-ui.net/)
- **[Motif Admin](https://base-ui.net/templates/motif-admin)** — the matching commerce operations dashboard: overview KPIs, orders, inventory, customers, analytics and settings. **$149** including Pro. [Live demo](https://dashboard-template.base-ui.net/overview)
- **Motif Suite** — both templates + one Pro license for **$199** (save $99 vs buying separately).

---

## 📦 What's included

| Category | Free | Pro |
| --- | --- | --- |
| **UI primitives** | 50+ (buttons, inputs, dialogs, hover cards, menubars, currency, kbd, tabs, calendar, toasts, …) | data table, date pickers, command palette, mega menu, file upload, multi-select, rich text editor, crop image, product gallery, tree, mention input, splitter |
| **Form blocks** | all 19 (login, signup, checkout, billing, wizard, …) | — |
| **Blocks & widgets** | — | blog/article cards, ecommerce blocks, media + social widgets |
| **Page layouts** | — | 15 (dashboard, kanban, inbox, docs, admin table, …) |
| **Directives, services, utils** | all | — |
| **Icons** | 390 SVG sprite icons | — |
| **Templates** | — | [Motif](https://base-ui.net/templates/motif) storefront + [Motif Admin](https://base-ui.net/templates/motif-admin) dashboard ($149 each, or Motif Suite $199) |

---

## 📋 Requirements

- **Node.js** 22+
- **Angular** 22+
- **Tailwind CSS** 4.x

### Server-side rendering

Components are safe to server-render or prerender. Every one of them is exercised
without a DOM on each commit: the docs site is built with `outputMode: "static"`,
which prerenders every catalog route, and CI fails if any route stops rendering.

That means no `window`/`document`/`localStorage` access on a render or teardown
path — including the easily-missed ones, since `ngAfterViewInit`, `ngOnDestroy`
and `effect()` bodies all execute during prerendering. The
[full write-up](https://base-ui.net/learn/angular-ssr-safe-component-library/)
covers what broke when we turned it on.

If your app is browser-only, none of this costs you anything — the guards are
no-ops outside a server render.

## 🤖 AI / LLM Reference

For AI agents and LLM-assisted development:

- **MCP server** — [`@lussos/base-ui-mcp`](https://www.npmjs.com/package/@lussos/base-ui-mcp): tools `list_components`, `search_components`, `get_component`, `add_components` (free tier, no license). Works with **Cursor**, **Claude** (Code/Desktop), **ChatGPT**, **Gemini**, **Kimi** (Kimi Code CLI), **VS Code** / GitHub Copilot, **Windsurf**, and other MCP hosts. Run `npx -y @lussos/base-ui-mcp` (stdio). Setup: [Getting started — AI agents (MCP)](https://base-ui.net/getting-started#ai-agents-mcp). The CLI remains the canonical installer; MCP wraps it.
- **Component catalog** — [`docs/ai/components.md`](docs/ai/components.md): selectors, inputs, outputs, and descriptions in one file. Published at [base-ui.net/docs/ai/components.md](https://base-ui.net/docs/ai/components.md) and inlined in [llms-full.txt](https://base-ui.net/llms-full.txt).
- **Cookbooks** — [base-ui.net/cookbooks](https://base-ui.net/cookbooks): assembled screens (settings form, dialog + CVA, invoice table, AI chat, Angular signal forms).
- **Non-interactive CLI** — `npx base-ui-cli init --yes` and `add --yes` for agent use. Agent index: [llms.txt](https://base-ui.net/llms.txt).

## 🔐 Security & vendor risk

- [SECURITY.md](SECURITY.md) — disclosure policy, every network request the CLI makes, and the supply-chain controls (tokenless releases, signed registry index, per-item digest verification, no install hooks) — including what is *not* covered.
- [Enterprise FAQ](docs/enterprise-faq.md) — what you actually depend on, offline/mirror options, continuity guarantees, and an honest account of what this project does *not* offer.

Verify a release yourself:

```bash
npm audit signatures                     # npm registry signature for base-ui-cli
BASE_UI_REQUIRE_SIGNATURE=1 npx base-ui-cli add button   # refuse unverified payloads
```

## 📄 License

See [LICENSE.md](LICENSE.md). In short: free-tier components are free to use in unlimited projects; pro components require a paid license (one developer, unlimited end products, lifetime updates); redistributing components as a library/kit is not permitted for either tier. Every component file the CLI installs carries a header naming its license.

Two guarantees worth calling out, because they are the usual objections to a commercial component library:

- **Perpetual use** (§5) — every version delivered to you stays usable forever, with no registry, CLI, or vendor dependency at build or run time. Each release also attaches an offline Pro source archive.
- **Termination does not reach shipped code** (§7) — a licensing dispute can stop future downloads, but never revokes your right to keep shipping products that already include the components.

The CLI *tool itself* ([`base-ui-cli`](https://www.npmjs.com/package/base-ui-cli)) is separately MIT-licensed — that covers only the tool's own code, not the components it fetches.

## 🆘 Support

Email support@base-ui.net.
