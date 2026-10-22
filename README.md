# Strategy Canvas

[Open the interactive demo](https://jingkang0822.github.io/strategy-canvas/)

Drag the nodes. Connect the logic. See the decision.

One strategy workspace: build a graph from the node library, arrange its steps,
inspect and edit a node, then run a local simulation and follow its captured
inputs, outputs and status. Your draft and results stay in your browser.

## Try it

1. Drag a node from the library onto the canvas, or click to add it.
2. Move nodes, connect their handles and open the inspector to edit them.
3. Tune CAPE/VIX inputs and watch the target allocation change.
4. Run the simulation, inspect node results, or try the source-failure scenario.
5. Refresh to resume your draft; Undo or confirm Restore template to recover.

## Demonstration data

The market snapshot, sample holdings and execution evidence are synthetic.
The target calculation uses the production frontend's TypeScript 4 × 4 regime
matrix. Custom analysis nodes emit labelled local demo results. The finite graph
simulation runs sequentially; it does not call a broker, market-data service or
remote AI model. No investment performance is claimed and no orders are sent.

## Architecture and delivery

React/TypeScript, shared React Flow canvas/node/edge components, the original graph
catalog and pure allocation matrix. A browser-local adapter owns the single draft
and simulation. Static relative assets support the GitHub Pages project path.

This repository contains inspected compiled artifacts only. Private product source,
configuration and history are not published. `site/release.json` records the release
identity and SHA-256 hashes; GitHub Actions verifies them before publication.
Source acceptance covers model tests, typechecking and real Chromium interaction
flows at desktop/mobile sizes, plus drag/drop, cancellation and storage recovery.

Publish updates by replacing only generated `site/` files with a verified build
and committing. The existing versioned browser storage namespace is retained for
visitor continuity. Bundled third-party license notices remain in the output.
