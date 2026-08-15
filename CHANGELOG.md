# Changelog

All notable changes to Reignition Tooling are documented here.

## [0.1.0] - 2026-08-15

First public release.

### Added

- **skrit-editor**: compiler warnings surfaced in the diagnostics panel
  (previously only hard errors were shown); outline navigation - click an
  entry to jump straight to its declaration in the source.
- **gas-editor**: snap-to-grid on canvas drag/resize; duplicate-widget;
  multi-select via ctrl-click and marquee-drag; native recognition of
  `.flick` files as GAS text (previously only `.gas` was recognized, even
  though `.flick` uses the identical format).
- **tank-editor**: drag-and-drop file add; a search/filter box across
  archive entries.

### Fixed

- **gas-editor**: demo-mode radio-group selection not being mutually
  exclusive.

## Pre-release development

The foundational work behind this first release, distilled:

- **gas-editor** - built out as a visual canvas editor for Dungeon Siege UI
  (GAS) interfaces, backed by a schema layer covering fuel documents,
  interfaces, messages, and rects. Grew an infinite pannable/zoomable
  canvas, era-authentic icon theming (Win98/XP/7) with a runtime picker,
  undo/redo, a live "Demo" preview mode (interact with the UI as it would
  actually behave, not just edit it statically), and generic (non-interface)
  GAS block-tree editing for files that aren't UI layouts. Along the way:
  fixed dead text inputs, a class of per-frame recompute bugs, and a crash
  on malformed action text.
- **skrit-editor** - built out as a visual editor for Skrit scripts: compile,
  inspect, and disassemble bytecode in one view. Fixed to run as a proper
  GUI subsystem application (no console flash on launch).
- **tank-editor** - scaffolded from nothing into a full archive
  browser/editor: folder-tree view, preview pane with syntax-highlighted
  text and a hex-dump fallback for binary entries, headless CLI subcommands
  alongside the GUI, and staged-edit resolution with full tank rebuild.
- **Shared** - a syntax-highlighting layer shared by `gas-editor` and
  `skrit-editor`, and a shared content-cache/UI-kit crate used across all
  three editors. Fixed a multi-line span bug, a duplicate-token bug, an
  O(n²) line-lookup bug, and icons losing their colour tint.
- Packaged all three editors as self-contained executables with embedded
  icons.
