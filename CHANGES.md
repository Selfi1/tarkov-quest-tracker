# Quest Tracker - Change Log

## Change History

### 2026-03-27

#### Change 1: Added Complete Quest Data
- **Time**: 14:30 (Initial setup)
- **What changed**: 
  - Added Lightkeeper quests (7 quests: Network Provider series + Snatch, Provocation, Make an Impression)
  - Added BTR Driver quests (6 quests: A Helping Hand + Shipping Delay Parts 1-5)
  - Removed Prapor custom override - now using full fallback data (~40 quests)
- **Why**: To populate all traders with their complete quest lists from the wiki fallback data
- **Files modified**: index.html (FALLBACK_QUESTS_BY_TRADER)

---

#### Change 2: Formatted Data for Readability
- **Time**: 14:35 (Code quality improvement)
- **What changed**:
  - Converted minified JSON (single 3000+ character line) to properly indented JavaScript object literal (~400 lines)
  - Maintained exact same data structure and functionality
- **Why**: Minified JSON was impossible to edit. Readability is essential for maintenance.
- **Files modified**: index.html (FALLBACK_QUESTS_BY_TRADER formatting)
- **Impact**: Zero functional change - same data, readable format

---

#### Change 3: Added 25 Missing Prapor Quests
- **Time**: 14:40 (Major content update)
- **What changed**:
  - Added 25 previously missing Prapor quests from wiki (tt-263 through tt-287)
  - New quests include: Shooting Cans, Luxurious Life, Properties All Around, Background Check, Belka and Strelka, No Questions Asked, You've Got Mail, Glory to CPSU (Part 1 & 2), Best Job in the World, Kings of the Rooftops, Green Corridor, Gendarmerie series (Mall Cop, Tickets Please, District Patrol), The Good Times (Part 1 & 2), Viewer, Hell on Earth (Part 1 & 2), Possessor, Forge a Friendship, Half-Empty, Stick in the Wheel, The Art of Explosion
  - Prapor now has 60 quests (up from 35)
- **Why**: User requested ALL quests in the tracker. This fills in significant gaps from the wiki data.
- **Files modified**: index.html (FALLBACK_QUESTS_BY_TRADER Prapor array)

---

#### Change 4: Added Missing Mechanic Quest & Cross-Referenced Community Data
- **Time**: 14:50 (Continued trader expansion + community verification)
- **What changed**:
  - Added Special Comms quest for Mechanic (tt-288)
  - Quest depends on Calibration (tt-217)
  - Mechanic now has 38 quests (up from 37)
  - Cross-referenced with EFT wiki official quest table (escapefromtarkov.fandom.com)
  - Verified against community quest databases (GitHub: Ropotov/tarkov-quests-json, mushipeas/tarkov-quests)
  - Searched Reddit r/EscapefromTarkov for comprehensive quest lists
- **Why**: Special Comms was missing from the tracker. Identified from wiki quest table. Comprehensive cross-reference ensures no major gaps.
- **Files modified**: index.html (FALLBACK_QUESTS_BY_TRADER Mechanic array)

---

#### Change 5: Added Auto-Complete for Prerequisite Quests
- **Time**: Later update
- **What changed**:
  - Completing a quest can now automatically mark prerequisite quests as completed when needed
  - Progress recomputation was improved so manual and automatic completions stay consistent
- **Why**: Large quest chains were too tedious to manage one quest at a time
- **Files modified**: index.html (quest progress logic)

---

#### Change 6: Allowed Completing Locked Quests With Prerequisites
- **Time**: Later update
- **What changed**:
  - Clicking a locked quest now fills in its prerequisite chain instead of blocking the action
- **Why**: Users often know what they have already done and want fast backfilling
- **Files modified**: index.html (quest toggle behavior)

---

#### Change 7: Replaced Fallback Quest Data With Comprehensive tarkov.dev Data
- **Time**: Major data update
- **What changed**:
  - Replaced the earlier partial quest dataset with a much larger tarkov.dev-based quest database
  - Expanded the tracker to 494 quests across 11 traders
  - Added Ref quests, expanded Lightkeeper and BTR Driver, and greatly expanded all major traders
  - Normalized quest IDs to trader-specific prefixes such as `pr-`, `th-`, `sk-`, `pk-`, `mc-`, `rf-`, `jail-`, `rg-`, `lk-`, and `bt-`
  - Added many cross-trader dependencies and faction-specific quest variants
- **Why**: The earlier dataset was incomplete and no longer matched the goal of tracking all quests
- **Files modified**: index.html (FALLBACK_QUESTS_BY_TRADER)

---

#### Change 8: Added Mouse Wheel Zoom
- **Time**: Usability update
- **What changed**:
  - Added wheel-based zoom in the quest canvas
  - Scrolling up zooms in and scrolling down zooms out
- **Why**: Manual zoom buttons alone were too slow for navigating large quest trees
- **Files modified**: index.html (view event handlers)

---

#### Change 9: Added Quest Search Bar
- **Time**: Usability update
- **What changed**:
  - Added a search input above the quest canvas
  - Search filters quest nodes in real time as the user types
- **Why**: With nearly 500 quests, manual scanning became inefficient
- **Files modified**: index.html (UI and render filtering)

---

#### Change 10: Added Level Requirement Display
- **Time**: Visibility update
- **What changed**:
  - Added computed level labels to quest nodes
  - Added level requirement information to quest tooltips
  - Level estimates are derived from quest dependency depth instead of a hardcoded data dump
- **Why**: Users needed a quick way to visually gauge quest progression depth
- **Files modified**: index.html (render and computed level logic)

---

#### Change 11: Improved Search Matching
- **Time**: Search quality update
- **What changed**:
  - Search now normalizes repeated spaces and trailing spaces
  - Partial phrase searches such as `The E` match reliably
- **Why**: Small spacing differences caused confusing missed results
- **Files modified**: index.html (search normalization)

---

#### Change 12: Added Global Search Across All Traders
- **Time**: Search feature expansion
- **What changed**:
  - Typing in the search box now shows matches from all traders
  - Search mode labels results by trader and changes the page title to `Search Results`
  - Added cycle-safe quest level calculation so imperfect dependency data cannot break global search rendering
- **Why**: Per-trader search was too limiting for a tracker of this size
- **Files modified**: index.html (render logic, search mode, level calculation)

---

## Current Quest Tracker Status (as of 2026-03-27)

### Total Quests: **494** across 11 traders

| Trader | Count | Status |
|--------|-------|--------|
| Prapor | 62 | ✅ Expanded |
| Therapist | 48 | ✅ Expanded |
| Fence | 15 | ✅ Expanded |
| Skier | 65 | ✅ Expanded |
| Peacekeeper | 47 | ✅ Expanded |
| Mechanic | 92 | ✅ Expanded |
| Ref | 17 | ✅ Added |
| Jaeger | 64 | ✅ Expanded |
| Ragman | 54 | ✅ Expanded |
| Lightkeeper | 14 | ✅ Expanded |
| BTR Driver | 16 | ✅ Expanded |

### Sources Used for Verification:
1. **tarkov.dev**: Primary source for the comprehensive quest refresh
2. **Official Wiki**: escapefromtarkov.fandom.com/wiki/Quests
3. **GitHub Community Databases**:
   - Ropotov/tarkov-quests-json (updated Sep 2025)
   - mushipeas/tarkov-quests 
4. **Reddit r/EscapefromTarkov**: Community quest discussions and references
5. **Embedded Fallback Data**: Original quest data from game archives

### Known Features:
- Quest dependencies properly mapped, including cross-trader dependencies
- Trader-specific quest ID naming conventions (`pr-`, `th-`, `sk-`, `pk-`, `mc-`, `rf-`, `jail-`, `rg-`, `lk-`, `bt-`)
- Auto-completion and prerequisite fill-in logic
- Mouse wheel zoom and button-based zoom controls
- Per-trader browsing plus global search across all traders
- Whitespace-tolerant live search
- Computed quest level labels and tooltips
- Responsive canvas-based quest chain visualization with bezier curves
- LocalStorage persistence for user progress

---

## Backup Points
Each change will create a timestamped backup automatically. To restore:
```
Copy index.html.backup-[timestamp] back to index.html
```

---

## Next Steps for Future Enhancements:
1. Monitor official wiki for new quests in patch updates
2. Verify exact dependency chains for edge case quests with unusual cross-trader or circular dependencies
3. Add quest reward information (currently data structure supports it, content not populated)
4. Implement quest filtering by difficulty/type
5. Add quest timeline visualization

---
