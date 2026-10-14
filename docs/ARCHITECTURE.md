# AI Players 26.32 — Architecture

## 1. Core Systems

### Main Controller
- Initializes the addon.
- Updates each AI independently.
- Prevents conflicting actions.
- Handles errors without crashing all AI players.

### Quest Manager
- Stores each AI's current quest.
- Checks requirements and unlock conditions.
- Prioritizes emergencies and player orders.
- Verifies completion before changing quest status.

### Perception System
- Scans the AI's field of view for blocks, mobs, players, and threats.
- Tracks visible targets and distance.
- Turns and looks around when no suitable target is found.
- Does not assume invisible targets are visible.

### Navigation System
- Finds safe destinations and paths.
- Avoids hazards and inaccessible routes.
- Allows jumping and safe pillar-building when needed.
- Stops an action if progress is impossible or unsafe.

### Inventory System
- Checks real inventory contents.
- Tracks available resources.
- Verifies collection, crafting, and consumption.
- Never reports an item as obtained without evidence.

### Action Systems
- Gathering: mines suitable blocks and collects drops.
- Crafting: uses valid recipes and available materials.
- Building: places blocks only when placement is safe.
- Combat: chooses targets, attacks, and defends.
- Exploration: searches for resources and safe locations.

### Debug System
- Shows each AI's current quest and action.
- Records successful and failed attempts.
- Explains why an action failed.
- Distinguishes tested features from untested features.

## 2. AI Update Order

Each AI update follows this priority order:

1. Handle immediate danger.
2. Follow a valid direct player order.
3. Continue an urgent existing action.
4. Check whether the current quest is complete.
5. Unlock eligible quests.
6. Select the highest-priority available quest.
7. Perform one or more safe actions.
8. Verify results and record them.

## 3. Multi-AI Design

- Every AI has its own quest state and inventory tracking.
- AI players must not share quest progress accidentally.
- AI players should avoid repeatedly choosing the same target when alternatives exist.
- Resource gathering and building must account for nearby AI players.
- Performance must be tested before increasing the population.

## 4. Implementation Rules

- Target Minecraft Education Edition 26.32.
- Avoid experimental features.
- Use vanilla-style visuals and real Minecraft items wherever possible.
- Verify API and component support before implementing features.
- Implement one small system at a time.
- Test each system in-game before building dependent systems.
- Never claim a feature works until it has been tested.

## 5. Development Stages

1. Confirm version compatibility and pack structure.
2. Spawn one custom AI entity.
3. Implement independent AI state and debug output.
4. Implement perception and safe movement.
5. Implement inventory checks and wood gathering.
6. Implement crafting and the initial quest chain.
7. Implement mining and combat.
8. Implement exploration and conditional quests.
9. Test multiple AI players.
10. Expand toward the target population of 16.