# AI Players 26.32 — Known Limitations

## Compatibility
- The target is Minecraft Education Edition 26.32.
- Script API methods and entity components must be checked against the target version.
- No experimental features should be required.
- Features that cannot work in this version must be documented rather than silently replaced.

## Player-Like Entities
- Addon entities are not genuine multiplayer player clients.
- Custom entities can imitate player appearance and behavior, but may not reproduce every player ability.
- Inventory, equipment, animations, and interactions depend on supported entity and scripting features.

## Perception
- A field of view must be implemented using supported entity positions and rotations.
- The addon may not know whether an arbitrary existing block was placed by a player or generated naturally.
- Targets outside the AI's detectable range cannot be treated as visible.

## Movement and Mining
- Minecraft navigation may not expose a complete pathfinding solution for every terrain type.
- Pillaring, jumping, and mining can fail because of terrain, placement rules, or missing resources.
- AI must stop unsafe actions rather than repeatedly attempting them.

## Inventory and Crafting
- Checking inventory does not automatically gather, craft, consume, or equip items.
- Every operation must verify its result.
- Recipe access and inventory manipulation must use APIs supported by the target version.

## Performance
- Sixteen AI entities performing frequent scans and navigation may cause lag.
- Scan frequency and AI update frequency must be measured in-game.
- Optimization must not make quest completion unreliable.

## Testing Status

All features begin as UNTESTED.

Use these statuses:
- UNTESTED — Not tested yet.
- PASS — Verified in-game.
- FAIL — Tested and failed.
- BLOCKED — Cannot proceed because of a known dependency or limitation.

Do not mark any feature PASS based only on code inspection.