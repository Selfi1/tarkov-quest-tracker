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

## Current Quest Tracker Status (as of 2026-03-27 14:50)

### Total Quests: **273** across 11 traders

| Trader | Count | Status |
|--------|-------|--------|
| Prapor | 60 | ✅ Comprehensive (was 35, added 25) |
| Therapist | 31 | ✅ Good (likely 1-2 more exist) |
| Mechanic | 38 | ✅ Complete  (just added tt-288) |
| Jaeger | 41 | ✅ Complete |
| Ragman | 32 | ✅ Complete |
| Skier | 27 | ✅ Complete |
| Peacekeeper | 29 | ✅ Complete |
| Lightkeeper | 7 | ✅ Complete |
| BTR Driver | 6 | ✅ Complete |
| Fence | 2 | ✅ Complete (only 2 exist) |
| Ref | 0 | ✅ Correct (operational tasks only) |

### Sources Used for Verification:
1. **Official Wiki**: escapefromtarkov.fandom.com/wiki/Quests (primary source for quest table)
2. **GitHub Community Databases**:
   - Ropotov/tarkov-quests-json (updated Sep 2025)
   - mushipeas/tarkov-quests 
3. **Reddit r/EscapefromTarkov**: Community quest discussions and references
4. **Embedded Fallback Data**: Original quest data from game archives

### Known Features:
- Quest dependencies properly mapped (requires arrays)
- Quest ID naming convention: `tt-0` through `tt-288`
- Auto-completion logic for dependent quests
- Responsive canvas-based visualizationwith bezier curves for quest chains
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
2. Verify exact dependency chains for edge case quests (tt-199, tt-200, tt-201 have complex multi-trader dependencies)
3. Add quest reward information (currently data structure supports it, content not populated)
4. Implement quest filtering by difficulty/type
5. Add quest timeline visualization

---
