# AI Players 26.32 — Test Checklist

All tests begin as UNTESTED.

## Stage 1 — Pack Compatibility
- [ ] Behavior pack imports successfully.
- [ ] Resource pack imports successfully.
- [ ] Both packs have distinct names and correct manifests.
- [ ] Packs load in Minecraft Education 26.32 without experimental features.
- [ ] No startup errors occur.

## Stage 2 — Basic AI
- [ ] One AI entity spawns.
- [ ] Its appearance and animations work.
- [ ] It has independent state.
- [ ] Its current quest can be inspected.
- [ ] Debug output reports real actions and results.

## Stage 3 — Perception and Movement
- [ ] AI detects targets in its field of view.
- [ ] AI turns and scans when no target is visible.
- [ ] AI moves toward safe destinations.
- [ ] AI does not repeatedly walk into obstacles.
- [ ] AI stops unsafe mining or block placement.

## Stage 4 — Wood Gathering
- [ ] AI identifies suitable trees.
- [ ] AI collects actual log drops.
- [ ] AI can jump to reach accessible logs.
- [ ] AI can safely pillar upward when necessary.
- [ ] AI stops when it cannot safely reach a tree.
- [ ] AI distinguishes tracked placed blocks from potential natural trees.

## Stage 5 — Crafting
- [ ] AI converts the required logs into planks.
- [ ] AI crafts and places a crafting table.
- [ ] AI crafts sticks.
- [ ] AI crafts a wooden pickaxe.
- [ ] Inventory changes are verified.

## Stage 6 — Mining and Equipment
- [ ] AI finds a safe route to stone.
- [ ] AI mines stone using a wooden pickaxe.
- [ ] AI collects 16 cobblestone.
- [ ] AI crafts a furnace, stone axe, stone pickaxe, and stone sword.
- [ ] The AI does not claim success when materials are missing.

## Stage 7 — Other Behaviors
- [ ] AI hunts passive mobs while on the ground.
- [ ] Hunting pauses while climbing.
- [ ] Emergency defense interrupts normal quests.
- [ ] Direct player orders take priority.
- [ ] Conditional quests unlock correctly.
- [ ] One-time quests do not repeat.
- [ ] Repeatable quests become available again when appropriate.

## Stage 8 — Multiple AI Players
- [ ] Four AI players work independently.
- [ ] Eight AI players work without major performance problems.
- [ ] Sixteen AI players work without major performance problems.
- [ ] AI players do not accidentally share quest progress.
- [ ] Debug output identifies which AI performed each action.

## Bug Record

For each failed test, record:
- Test name
- Expected behavior
- Actual behavior
- Error message, if any
- Steps to reproduce
- Fix attempted
- Retest result