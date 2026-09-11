# Development Roadmap

## Phase 1: MVP (Minimum Viable Product)
The goal of this phase is a fully client-side, read-only market visualizer.

- [ ] **Step 1: Base Skeleton & Dependency Setup**
  - Init Tauri + Vite project.
  - Clean out boilerplate CSS/JS.
  - Verify Void Linux incremental build works.
- [ ] **Step 2: API Client & Local Caching**
  - Implement Rust logic to fetch `/mapping` (item names/IDs).
  - Implement Rust logic to fetch `/latest` (current prices).
  - Cache `mapping` locally to avoid redundant downloads.
- [ ] **Step 3: The Index (Item Grid)**
  - Build the virtualized left-pane list.
  - Populate with item names and current margins from the API.
  - Add a fast, sticky text filter/search bar.
- [ ] **Step 4: The Canvas (Chart Panel)**
  - Implement Lightweight Charts (or similar minimal charting lib) in the main pane.
  - Wire UI so clicking an item triggers a Rust fetch to `/timeseries`.
  - Render the candlestick/line chart data seamlessly.

## Phase 2: Future Scope (Do Not Implement Yet)
- [ ] Clickable buy/sell target crosshairs.
- [ ] Automated 2% GE tax profit calculations.
- [ ] Local SQLite database for "Favorites" filtering.
- [ ] Oracle Cloud WebSocket integration for live market pulse.
