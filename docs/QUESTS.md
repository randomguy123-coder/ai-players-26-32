# AI Players 26.32 — Quest System

## Quest Rules

- Every quest has a unique ID.
- Quests can be locked, available, active, completed, or failed.
- A quest can only start when its requirements are met.
- Completing a quest must be verified before unlocking the next quest.
- One-time quests cannot repeat after completion.
- Repeatable quests can become available again.
- Emergency defense and direct player orders can interrupt normal quests.
- Each AI records its current quest, last action, result, and next action.
- Failed actions must not be reported as successful.

## Initial Survival Quest Chain

### Q001 — Chop the First Tree
- Type: One-time
- Requirement: None
- Goal: Collect logs from one tree.
- Completion: The AI has collected logs from a tree.

### Q002 — Gather More Wood
- Type: One-time
- Requirement: Q001 completed
- Goal: Collect logs from nine additional trees.
- Completion: Nine additional trees have been harvested.

### Q003 — Prepare Crafting Materials
- Type: One-time
- Requirement: Q002 completed
- Goals:
  1. Convert three-quarters of the collected logs into planks, rounding up.
  2. Craft a crafting table using four planks.
  3. Place the crafting table.
  4. Craft eight sticks using four planks.
- Completion: The crafting table is placed and eight sticks have been crafted.

### Q004 — Craft a Wooden Pickaxe
- Type: One-time
- Requirement: Q003 completed
- Goal: Craft a wooden pickaxe using three planks and two sticks.
- Completion: The pickaxe exists in the AI's inventory.

### Q005 — Find Stone
- Type: One-time
- Requirement: Q004 completed
- Goal: Locate a safe route to stone.
- Exploration: Scan the field of view, look around if no target is visible, then choose a safe destination within 60 blocks.
- Completion: The AI reaches a location with accessible stone.

### Q006 — Gather Cobblestone
- Type: One-time
- Requirement: Q005 completed
- Goal: Safely mine 16 cobblestone.
- Safety: Never dig straight down. Stop or find another route if mining becomes unsafe.
- Completion: The AI has 16 cobblestone.

### Q007 — Craft Stone Equipment
- Type: One-time
- Requirement: Q006 completed
- Goals: Craft one furnace, one stone axe, one stone pickaxe, and one stone sword.
- Completion: All four items are verified in the inventory.

## Other Quests

### Q100 — Hunt Passive Mobs
- Type: Repeatable
- Requirement: AI is on the ground and not climbing.
- Goal: Hunt visible passive mobs, such as cows, pigs, sheep, and chickens, and collect useful drops.
- Priority: Lower than emergency defense and direct player orders.
- Completion: The current hunt ends when the target is defeated, lost, or unreachable.

### Q200 — Explore
- Type: Repeatable
- Requirement: No suitable target is visible and no higher-priority task needs attention.
- Goal: Look around and travel to a safe destination within 60 blocks of the current exploration center.
- Rule: After three successful exploration moves, begin the stone-gathering phase if Q004 is complete.
- Completion: The destination is reached safely.

## Resource and World Rules

- Use real Minecraft items wherever supported.
- Check actual inventory before crafting or consuming resources.
- Do not assume an item was collected just because a mining action was attempted.
- Track blocks placed by AI players when possible.
- Minecraft does not universally identify whether a block was placed by a player or generated naturally. Untracked logs must not automatically be assumed to be natural trees.
- Tree climbing and pillar-building must use available blocks and safe placement checks.
- Do not hunt passive mobs while climbing.
- Direct player orders and emergency defense take priority over ordinary gathering and exploration.

## Quest Logging

For every quest transition, record:
- AI identifier
- Quest ID
- Previous and new status
- Requirements checked
- Last attempted action
- Verified result
- Reason for failure, if any
- Next planned action