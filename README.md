# Tarkov Quest Tracker

Interactive Escape from Tarkov quest tracker with trader quest trees, dependency visualization, persistent progress, and global search.

## Features

- Tracks 498 quests across 11 traders
- Visual quest graph with dependency lines
- Color-coded quest states: completed, available, locked, and failed
- Auto-fills prerequisite quests when marking progress
- Supports branch-aware quest logic with `requires`, `requiresAny`, and `fails`
- Highlights Collector-required quests with a gold `C` badge
- Mouse wheel zoom and drag-to-pan navigation
- Trader-specific browsing and global search across all traders
- Computed level labels on quest nodes
- Import and export of progress data
- Browser-based local save support with LocalStorage

## Traders Included

- Prapor
- Therapist
- Fence
- Skier
- Peacekeeper
- Mechanic
- Ref
- Jaeger
- Ragman
- Lightkeeper
- BTR Driver

## Controls

- Click a quest to mark it completed
- Click a completed quest to remove manual completion
- Clicking a locked quest can backfill its prerequisite chain automatically
- Scroll inside the quest canvas to zoom
- Drag the canvas to pan around the quest tree
- Use the search bar to find quests by name
- Use Export and Import to move progress between browsers or devices

## Search Behavior

- Empty search: shows the currently selected trader
- Active search: shows matching quests from all traders
- Search is case-insensitive and whitespace-tolerant

## Data Notes

- Quest data has been expanded using tarkov.dev as the primary source
- Collector prerequisites are aligned to live tarkov.dev `taskRequirements` data
- Trader branch conflicts and OR-prerequisite paths are modeled directly in the local dataset
- Some quest level labels are estimated from dependency depth for readability
- Cross-trader dependencies are supported where data is available

## Recent Changes

- Corrected Therapist, Fence, and Ref dependency chains using wiki-backed validation
- Added missing Ref quests and removed a stale Ref quest entry that caused graph issues
- Expanded the Prapor `Test Drive` chain through Part 6 so Collector prerequisites resolve locally
- Rebuilt the Collector prerequisite list from live tarkov.dev data and marked those quests in the UI

## Files

- [index.html](index.html): main application
- [CHANGES.md](CHANGES.md): project change log

## Running Locally

Open [index.html](index.html) in a browser.

No build step or package installation is required.

## Version Milestones

- `v0.1.0`: initial tracker foundation
- `v0.2.0`: major quest database expansion from tarkov.dev
- `v0.3.0`: search, zoom, level labels, and documentation improvements
- `v0.4.0`: branch-aware dependency fixes, Collector alignment, and Collector-required quest badges
