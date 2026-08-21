# Changelog

Library, CLI, and MCP updates for [Base UI](https://base-ui.net) — free and Pro components,
generated from conventional commits that touch `projects/base/src`, `packages/cli/src`,
`packages/mcp/src`, or `server/pro-registry`.

Demo-site, SEO, analytics, and AI-doc tooling commits are omitted.

Also published at [https://base-ui.net/changelog](https://base-ui.net/changelog).

## August 2026

- **Chores** — add angular-eslint so ng lint actually runs.
- **Other** — Isolate product-card hover so sibling cards in a row do not react.
- **Other** — Add hover-open nested menubar menus and stay-open selectable items.
- **Chores** — **mcp:** bump zod to 4.4.3
- **Chores** — bump tailwind-merge to 3.6.0
- **Other** — Point the product at the public GitHub hub and add community guardrails.
- **Bug Fixes** — **cli:** keep fetch out of the published bin entry
- **Features** — persist shareable demo themes and close flagship form/a11y gaps
- **Bug Fixes** — **cli:** fetch the registry index once for diff and update
- **Features** — add hover-card, menubar, loading-overlay, currency-input, kbd, aspect-ratio, scroll-area, and cookie-banner
- **Features** — add labeled shell nav sections that collapse with the dashboard rail
- **Bug Fixes** — keep hover-card open on panel click and correct menubar and currency input
- **Chores** — update documentation and changelog for Angular 22 migration
- **Chores** — upgrade Angular 21 to 22.1
- **Bug Fixes** — **cli:** drop shell access and ship a zero-dependency tarball
- **Chores** — update .gitignore and optimize build process
- **Features** — add combobox, tags-input, time-picker, and chat to the registry
- **Bug Fixes** — **scroll-nav:** use one scrollport with a sticky sidebar
- **Chores** — serve pro registry on pro.base-ui.net
- **Chores** — remove @lussos package names
- **Bug Fixes** — **breadcrumb:** truncate current crumb on one row
- **Refactors** — **shell:** move backdrop logic inside main column for improved mobile handling
- **Bug Fixes** — **app:** restore nested scroll on navigate and browser back
- **Features** — **cli:** verify registry payloads before writing them to disk
- **Documentation** — **api:** show CLI-local imports instead of deprecated @lussos/base-ui
- **Features** — **shell:** unify page and dashboard shells into base-shell
- **Features** — **responsive-nav:** add responsive navigation components
- **Features** — **stat-card:** introduce metric variant with delta pill and sparkline
- **Features** — **lightbox:** add free lightbox gallery with alt-initials fallback
- **Features** — **countdown:** enhance countdown component with SSR support and client ticker
- **Features** — **shell:** add dashboard-shell and page-shell components with services
- **Features** — **buttons:** add progress-button with stable-width loading spinner
- **Bug Fixes** — **html:** correct utility class name mistakes in various components

## July 2026

- **Refactors** — **tooltip:** rename `placement` to `tooltipPlacement` for clarity and avoid conflicts
- **Features** — add EcommerceBlockProductCard component and implement product demo showcase in Ecommerce page
- **Features** — **pro:** add chart and virtual-scroll components; fix Base import path for CLI
- **Bug Fixes** — prerender the whole site — timer leaks, SSR crash, and Pro a11y gaps
- **Features** — **dropdown:** support cascading nested menus without closing the parent
- **Bug Fixes** — add SSR safety guards to components and enable server-side rendering support
- **Other** — mcp added
- **Features** — implement comprehensive component unit tests and standardize test configurations across the library
- **Refactors** — make ThemeService SSR-safe by isolating DOM and localStorage access to the browser platform
- **Features** — **base:** add Pro knob dial and free ripple directive
- **Bug Fixes** — **base:** break button-group circular import for Karma
- **Features** — **base:** add free input-mask directive with demo page
- **Features** — **base:** add Pro select-tree and document form-control height rules
- **Features** — **base:** add free speed-dial FAB with demo page
- **Features** — **base:** add Pro pick-list dual-listbox with demo page
- **Features** — **base:** add free tri-state checkbox with demo page
- **Features** — enhance base elements with size options, popups and file-manager improvements
- **Features** — **base:** add free context-menu component
- **Features** — **base:** add meter-group, dual-range-slider, and progress tip
- **Features** — enable dynamic tooltip updates and add reactive copy status to code component
- **Refactors** — move advanced components from free to pro tier and document new dual-range-slider and splitter components
- **Features** — **base:** add Pro layout-file-manager application
- **Features** — **base:** add free scroll-top/bottom and polish demos
- **Features** — **base:** add free splitter with demo page
- **Features** — **base:** add Pro layout-scheduler full calendar
- **Features** — **cli:** add diff/update commands for upstream component changes
- **Features** — **catalog:** split registry into free/pro categories, promote Sidenav/ScrollNav to library
- **Bug Fixes** — **cli:** harden diff/update follow-ups and add unit tests
- **Features** — **base:** add free rich-text-editor component
- **Bug Fixes** — **button:** important text colors so anchor buttons beat prose typography
- **Features** — **pro-registry:** authenticated worker serving pro components
- **Features** — **cli:** rename to base-ui-cli with recursive add, list command, working init
- **Bug Fixes** — replace arbitrary spacing values with standard classes in media widgets
- **Bug Fixes** — update button color in social-widget-image-caption
- **Refactors** — enhance ScrollNav to support nested scroll containers and add resetSidenavScroll for navigation changes
- **Features** — add social widget components
- **Bug Fixes** — adjust styling in media widget video and album components
- **Features** — extract 16 premium blog/magazine card components
- **Bug Fixes** — remove unused imports in blog cards and fix unclosed div in demo page
- **Features** — visually enhance blog/magazine cards to a premium editorial design system
- **Refactors** — migrate to standard tailwind spacing and classes
- **Chores** — sync component and layout updates
- **Features** — implement a11y keyboard navigation utility and enhance component accessibility
- **Refactors** — apply booleanAttribute and numberAttribute across component library
- **Chores** — push fixes to registry and finalize component updates
- **Bug Fixes** — resolve broken class bindings due to object literal syntax
- **Chores** — sync layouts with components and update paid/free tiers registry
- **Other** — code update
- **Features** — add inbox messaging layout and introduce icon variant to file upload component
- **Features** — **layouts, a11y:** add docs-kb layout and improve accessibility for command-palette and toggle
- **Features** — **layouts, core:** sync admin-data-table, checkbox, button and test updates
- **Bug Fixes** — **tree:** update sizing of icons in tree component
- **Features** — **layouts:** add settings layout and update dashboard layout to library
- **Bug Fixes** — **layout:** sync onboarding flow updates to library and fix missing imports
- **Bug Fixes** — **stepper:** add max-width and center alignment, fix template signal
- **Bug Fixes** — **layout:** fix BaseAddonEndDirective import name
- **Bug Fixes** — **layout:** add max-width to layout-onboarding-flow stepper wrapper
- **Tests** — update component test files
- **Bug Fixes** — **stepper:** move max-width to layout wrapper
- **Features** — **library:** add layout-bento-grid to paid tier and update toast
- **Features** — **library:** add layout-kanban-board, layout-pricing, and layout-split-screen to paid tier
- **Bug Fixes** — **color-picker:** add cursor-pointer to trigger button
- **Bug Fixes** — **color-picker:** improve input widths in custom color panel
- **Features** — add layout-dashboard to premium library components
- **Bug Fixes** — **dialog:** update dialog template, fix imports in product quick view feat(library): add layout-portfolio-gallery with dialogs to paid tier
- **Bug Fixes** — **drawer:** correct close icon name feat(hero-features): bundle hero-demo-dialog with layout-hero-features
- **Features** — **library:** add layout-magazine-grid to paid tier components
- **Features** — **library:** add layout-ecommerce-grid to paid tier components
- **Features** — **library:** add layout-blog-sidebar to paid tier components
- **Bug Fixes** — **library:** correct import paths in portfolio gallery components
- **Other** — dynamically add styles and icons
- **Features** — add team-invite, billing, delete-account, wizard, and filter forms
- **Other** — list-item cursor pointer
- **Features** — add comprehensive suite of reusable form components to the base library
- **Other** — update registry
- **Other** — gemini fixes
- **Other** — update library zoneless and npx i component
- **Other** — some fixes
- **Features** — install CLI dependencies and update base component templates

## June 2026

- **Other** — new components and fixing issues
- **Other** — migration 2
- **Other** — migration a21
- **Other** — migration 5
- **Other** — angular migration to 21
- **Other** — computed migration 21
- **Other** — migration 4
- **Other** — migration 3
- **Other** — migration to angular 21
- **Bug Fixes** — **otp-input:** fill-all-fields bug + backspace navigation
- **Other** —              update sintax to angular 21
- **Refactors** — **library:** migrate all components to Angular signal-based APIs
- **Features** — **avatar-group:** tighter default overlap with hover-spread animation
- **Features** — six framework improvements — cn() override, standalone bootstrap, tests, Storybook, Tailwind v4, focus trap
- **Features** — add 10 new library components with demo pages
- **Bug Fixes** — **popover:** fully self-contained component — panel never permanently visible
- **Bug Fixes** — **popover:** rewrite with fixed viewport positioning — always on top, properly dismissable
- **Bug Fixes** — **color-picker:** use fixed viewport-relative positioning for panel

## May 2026

- **Other** — new UI elements
- **Other** — updates for AI
- **Other** — AI related updates
- **Other** — components update
- **Other** — update compoents for ai
- **Other** — added contact form
- **Other** — crop image update
- **Other** — lussos ui library component AI ready
- **Other** — some UI updates
- **Other** — Ai updates
- **Other** — forms added
- **Other** — icon update
- **Other** — media done and some library updates
- **Other** — small ui updates
- **Other** — http to https
- **Other** — test
- **Other** — code snipet update
- **Other** — empty states
- **Other** — test

## April 2026

- **Other** — Articles and some componetnts updates
- **Other** — updates on API references
- **Other** — updates base files
- **Other** — home page added

## March 2026

- **Other** — npm base
