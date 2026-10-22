# IB Strategy Desk — Interactive Portfolio

[Open the interactive demo](https://jingkang0822.github.io/ib-strategy-demo/)

Explore a rule-based strategy workspace: edit CAPE/VIX inputs, arrange its
dependency graph, and inspect successful, failed, or cancelled execution replays.
Changes and history stay in your own browser.

## What is real, and what is illustrative

The allocation calculation uses the same TypeScript 4 × 4 regime matrix as the
production frontend. The market observations, strategy presets and execution
traces are synthetic. No login, brokerage account, trading API, remote AI service
or application server is involved. No investment performance is claimed.

## Try it

1. Open Strategy and choose a preset. Change CAPE or VIX and watch target weights.
2. Drag or inspect nodes. Remove a connection to see validation; Restore template
   recovers a runnable dependency graph.
3. Run a successful calculation or an injected source failure. Inspect captured
   inputs, node outputs and terminal status in Run history.
4. Refresh to confirm browser-local persistence, or explicitly Reset demo workspace.

## Architecture and delivery

The demo reuses React/TypeScript presentation components, React Flow graph
rendering, the SVG chart, an accessible modal, the graph template and the pure
allocation matrix from the product. A separate browser-local adapter owns demo
state and finite sequential replay. Hash navigation and relative assets support
GitHub Pages project paths.

This repository contains the inspected, compiled public artifact only; private
product source, configuration and history are not published. `site/release.json`
records the SHA-256 identity and exact static file hashes. The deployment workflow
verifies these hashes before publishing. Product source acceptance includes unit
tests, typechecking and real Chromium interaction tests at desktop/mobile sizes,
plus storage failure, cancellation, reset and reload scenarios.

## Publish an updated artifact

Replace only the generated `site/` files with a newly verified build, retaining
`release.json`, and commit. GitHub Actions deploys `site/` to Pages. Existing
browser state is versioned under `ib-strategy-showcase:v1`; the UI offers an
explicit reset. Bundled third-party license notices are retained in the output.
