# Tarkov Quest Tracker

Interactive Escape from Tarkov quest tracker with trader quest trees, dependency visualization, persistent progress, and global search.

## Features

- Tracks 494 quests across 11 traders
- Visual quest graph with dependency lines
- Color-coded quest states: completed, available, and locked
- Auto-fills prerequisite quests when marking progress
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
- Some quest level labels are estimated from dependency depth for readability
- Cross-trader dependencies are supported where data is available

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
