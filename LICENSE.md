# Base UI License

Copyright (c) 2026 Lussos. All rights reserved.

Base UI is a commercial product with a free tier. This license governs both. By using Base UI (via the `base-ui-cli`, the registry at base-ui.net, or this repository) you agree to these terms.

*This document is a plain-language license summary written for developers. It is not a substitute for legal review.*

## 1. Free-tier components

Components marked **free** in the registry may be used by anyone, without an account or payment:

- ✅ Use in unlimited personal, commercial, and open-source **end products** (websites, applications, and similar), for yourself or for clients.
- ✅ Modify the copied source freely — the code copied into your project is yours to adapt.
- ❌ Do not republish or redistribute the components themselves (e.g. as a UI library, component collection, template kit, Figma/Sketch kit, or website builder), whether free or paid.

## 2. Pro components (paid license required)

Components marked **pro** require a valid license key.

**Personal license** — one named developer:

- ✅ Use in unlimited end products, for yourself or for clients, commercial or open-source.
- ✅ Lifetime access to all pro components available today and added in the future, including updates.
- ❌ Do not share your license key. One license covers one developer.

**Team license** — up to 10 named developers within one organization:

- ✅ Everything in the personal license, for up to 10 developers who are employees or contractors of the licensee.
- ✅ End products must belong to the licensee or its clients.

## 3. Prohibited for all tiers

- ❌ Redistributing, republishing, or reselling Base UI components separately from an end product — including as part of a derivative or competing UI library, component kit, template collection, design kit, or website-builder content.
- ❌ Sharing license keys, accounts, or authenticated registry access with anyone not covered by the license.
- ❌ Removing or circumventing the license validation of the pro registry.

In short: build **anything you like** with Base UI, as long as what you distribute is an end product and not the components themselves.

## 4. Refunds

If Base UI isn't working out, contact support@base-ui.net within **14 days** of purchase for a full refund. Refunds are not offered where there is evidence of redistribution or license abuse.

## 5. Updates, support, and continuity

Paid licenses include lifetime access to updates of the pro catalog.

**What is guaranteed.** Every version of a pro component delivered to you remains yours to use, modify, and ship in end products **in perpetuity**. That right does not expire, does not depend on the registry staying online, and does not require the CLI, this repository, or Lussos to continue existing. Pro components are plain source files copied into your repository — they contain no license check, no activation, and no runtime call to any Base UI service. If everything here disappeared tomorrow, your build would keep working.

**What is best-effort.** New releases, bug fixes, and support via GitHub issues and support@base-ui.net are provided on a best-effort basis. There is no uptime or response-time guarantee unless separately agreed in writing.

**Continuity.** If the pro registry is unavailable for more than 30 consecutive days, or Base UI is discontinued, then for any customer with a valid license at that time:

- The perpetual rights in this section continue unchanged.
- Lussos will make the pro component source available by an alternative means (a downloadable archive, a private repository, or a public source release), so that registry availability is never the only path to code you have already paid for.
- Section 3's redistribution restrictions still apply.

Per-release source archives are attached to [GitHub Releases](https://github.com/Base-ui-ng/base-theme/releases) so licensees can retain an offline copy at any time, without waiting for a discontinuation event.

## 6. Warranty and liability

Base UI is provided **"as is"**, without warranty of any kind, express or implied, including merchantability, fitness for a particular purpose, and non-infringement. In no event shall Lussos be liable for any claim, damages, or other liability arising from the use of Base UI. Your sole remedy is the refund described in section 4.

## 7. Termination

Violating these terms (in particular section 3) terminates your license immediately.

**Termination does not reach code you have already shipped.** It ends your right to download new pro components and to receive updates. It does **not** revoke your right to continue using, modifying, distributing, and supporting pro components already incorporated into end products before termination. Software you have released stays releasable; you never have to recall, re-license, or rewrite a shipped product because of a dispute over this license.

Sections 3, 5 (perpetual use), and 6 survive termination.

## Component of this repository

The CLI *tool* (`packages/cli`, published to npm as [`base-ui-cli`](https://www.npmjs.com/package/base-ui-cli)) is separately licensed under the MIT license — see [`packages/cli/LICENSE`](packages/cli/LICENSE). That MIT license covers only the CLI's own source code (argument parsing, fetching, writing files to disk). It does **not** extend to the components, blocks, or other content the CLI fetches and installs — those remain governed by this document (sections 1–3 above) regardless of which tier they belong to. Every file the CLI writes carries a short header identifying its own license and linking back here.
