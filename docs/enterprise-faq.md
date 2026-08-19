# Enterprise FAQ

Written for the person doing a build-versus-buy review, a security review, or a
vendor-risk assessment. It answers the hard questions directly, including the
ones where the honest answer is not flattering.

---

## What am I actually depending on?

There are two distribution paths, and they carry very different risk.

**The CLI path (recommended for enterprise).** `npx base-ui-cli add button`
copies plain Angular + Tailwind source files into your repository. After that:

- The code is in your version control, reviewed in your pull requests.
- Your build has **no dependency on Base UI at all** — no package in
  `node_modules`, no import of a vendor namespace, no network call at build time
  or run time.
- Deleting the CLI from your machine changes nothing about your application.
- You can edit any file freely; `npx base-ui-cli diff` still shows you what
  changed upstream, and `update` lets you take or ignore it per file.

**There is no npm library path.** Copy-in via `base-ui-cli` is the only supported
way to consume Base UI. There is no second mode in which you take on a runtime
dependency on a vendor package.

## Is there any phone-home, telemetry, or license check in the components?

No. The component source contains no license validation, no activation, no
analytics, and no call to any Base UI service. Licensing is enforced
server-side at download time, once. After a component is on your disk it is
inert source code.

The CLI itself makes outbound `GET` requests only, and never transmits your
code, environment, or any identifier. See [SECURITY.md](../SECURITY.md) for the
full request table and how to disable the update check.

## How do I verify the CLI is what you say it is?

```bash
npm audit signatures      # npm's registry signature over the tarball
npm pack base-ui-cli && tar -tzf base-ui-cli-*.tgz    # exactly 4 entries
node -e "console.log(require('base-ui-cli/package.json').scripts)"   # no install hooks
```

You will not find a Sigstore provenance attestation. npm does not issue them for
packages built from a private source repository, and this repository is private
because it holds the pro catalog. Publishing is instead restricted to one GitHub
Actions workflow via OIDC, with no long-lived token in existence. If provenance
is a hard procurement requirement, say so before buying — we would rather lose
the sale than have you discover it during a security review.

The package declares no `preinstall`/`postinstall`/`prepare` script, so
installing it executes no code. Registry downloads are digest-verified against a
signed index before a single byte is written to disk; set
`BASE_UI_REQUIRE_SIGNATURE=1` to make verification mandatory in CI.

## Can I mirror the registry internally?

Yes. Point `BASE_UI_REGISTRY_URL` (and `BASE_UI_PRO_REGISTRY_URL` for Pro) at
your own host serving the same JSON layout. Every release also ships an offline
Pro payload archive — see the continuity section below.

## The project has one main maintainer. Is that a problem?

It is one maintainer, and pretending otherwise would be dishonest. Roughly 90% of
commits come from a single person. If you need a vendor with a staffed support
organization and contractual SLAs, that is a legitimate reason to choose
something else.

What that risk does *and does not* mean here:

| Risk | Applies? |
|---|---|
| Vendor disappears and your build breaks | **No.** Components are source in your repo with no runtime dependency. |
| Vendor disappears and you cannot get security fixes from them | **Yes.** You would maintain the copied source yourself — which you can, because you have it. |
| A dependency you cannot patch goes unmaintained | **No.** You own the files and can edit them like any other code in your repository. |
| Slow response to bug reports or feature requests | **Yes.** Support is best-effort; see LICENSE.md §5. |

The copy-in architecture is what bounds the blast radius. The worst realistic
case is that you stop receiving updates and inherit maintenance of code you
already have, in a stack (Angular + Tailwind) your team already knows. That is a
materially different failure mode from an abandoned runtime dependency.

## What happens if the project shuts down or the registry goes offline?

[LICENSE.md §5](../LICENSE.md) makes this contractual rather than a promise:

- Every version delivered to you is yours **in perpetuity** — the right does not
  expire and does not depend on the registry, the CLI, or Lussos continuing to
  exist.
- If the registry is unavailable for more than 30 consecutive days, or the
  product is discontinued, Pro source is made available by another means.
- You do not have to wait for that event: every library release attaches a Pro
  source archive to a GitHub Release, so you can keep an offline copy from day
  one. The archive includes instructions for installing from it with no network
  access.

## Does a license dispute put my shipped software at risk?

No. [LICENSE.md §7](../LICENSE.md) explicitly carves this out: termination ends
your right to download new components and receive updates, and never revokes
your right to keep using, modifying, distributing, and supporting components
already incorporated into products you have shipped. You will never have to
recall, re-license, or rewrite a released product over a licensing dispute.

## What exactly is proprietary?

| Layer | License |
|---|---|
| `base-ui-cli` (the tool) | MIT |
| Free-tier components | Free for unlimited commercial use; may not be redistributed *as a component library* |
| Pro components | Paid license; same product freedom, same redistribution limit |

The restriction in every tier is on reselling the components themselves as a
competing UI kit, template collection, or design kit. Building and selling
products with them is unrestricted, including client work.

## What is not offered?

Stating the gaps plainly, so they surface in review rather than after purchase:

- No uptime or response-time SLA unless separately agreed in writing.
- No formal security certification (no SOC 2, no ISO 27001).
- No 24/7 support rotation.
- No guarantee of a specific release cadence.

If your procurement process requires any of these, contact
support@base-ui.net before purchasing rather than assuming they can be added
later.

## Reporting a security issue

security@base-ui.net. See [SECURITY.md](../SECURITY.md) for scope, response
targets, and disclosure expectations.
