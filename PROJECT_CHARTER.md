## Project Identity

* **Core Goal:** Build a blazing-fast, native desktop application for visualizing Old School RuneScape market data.
* **Design Philosophy:** Tiling window manager and terminal-inspired UI. The interface must be modular, heavily reliant on strict grid layouts, and instantly resizable.
* **MVP Scope:** Fetch `/mapping` and `/latest` on boot, display a virtualized searchable grid, and lazily load `/timeseries` data into a high-performance chart on item click.

## Architecture & Tech Stack

* **OS Environment:** Void Linux executing strictly via the `zsh` shell.
* **Core Framework:** Tauri (Rust backend, lightweight frontend).
* **Dependency Rule:** Keep dependencies minimal. No complex virtual environments (e.g., Python `venv`). Rely on native binaries and fast build tools like Vite.
* **Performance:** UI rendering must be offloaded to virtualized lists to handle 4000+ items without memory bloat or lag.

## API & Data Guidelines

* **Rate Limit Respect:** Never spam the Wiki API. Utilize bulk endpoints effectively.
* **Smart Caching:** Cache static data like item `mapping` locally.
* **Lazy Loading:** Only ping the `/timeseries` endpoint for specific historical data when an item is actively clicked in the UI.

## Gem Workflow Rules

* **Scope Strictness:** Implement exactly one feature per session. Do not hallucinate future scope.
* **Zsh Safety:** All automated implementation scripts must use quoted heredocs (`cat << 'EOF' > filepath`) to prevent zsh from prematurely expanding variables.
* **Zero-Friction Execution:** Every response must end with a single, copy-pasteable terminal block that writes the necessary files and immediately executes a test or build command (e.g., `cargo tauri dev`).

## Context & State Management:

*  Always read ROADMAP.md before generating code.
*  Identify the first unchecked box ([ ]). That is the current active feature.
* Do not jump ahead. Only write code for the current active feature.
* When providing your final terminal block, include a sed command or instructions to update the ROADMAP.md checkbox  	from [ ] to [x] for the completed feature, so it is included in the final git commit.
