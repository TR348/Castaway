Castaway Island — Design
Date: 2026-07-05 Status: Implemented (v3 — two-island escape arc, weather roll-in, spear/chop/smash animations, pause)

Goal
A browser survival game in the style of the classic Johnny Castaway screensaver (EGA pixel-art look, per the user's reference pictures). Runs on PC, tablet, and phone with no install and no external assets.

Technology
Single self-contained index.html: HTML5 Canvas 2D + vanilla JavaScript.
All sprites are procedural EGA-palette pixel art (string maps rendered to offscreen canvases). No copyrighted assets are copied.
All audio is synthesized with WebAudio (waves loop, grunts, gull cries, splashes, chomp, thunder, plane drone, jingles) — no sound files.
"3D" interpreted as layered 2.5D depth (sky / horizon / sea bands / island / actors / night tint); true WebGL 3D would not match the reference art.
Responsive: logical 512x320 canvas scaled to fit any window, pixelated rendering. Keyboard (arrows/AD + E/Space/B/T/P), click/tap-to-move on the ground, and touch buttons (◀ ▶ / ACT / BUILD / SCOPE); tap gulls to scare.
Pause: P key or the ⏸ button (top-right) freezes the game and suspends audio.
World
Side-view world 1600px wide; island in the middle (walkable ~x591–1009), sea on both sides. Camera follows the player. Day/night cycle (150 s/day): the sun rises and sets below the horizon, then the moon rises with a shimmering moonlight reflection trail on the sea (per the user's reference picture).

Game arc
Escape the island by building a raft. The first escape lands the castaway on a SECOND island (also three palms — the raft visibly splinters and sinks on arrival, animated planks and all) and he starts again with nothing; the HUD shows "ISLE 2" and the day counter keeps the survival streak. Escaping the second island reaches the shipping lanes: the WIN screen shows days survived across both islands, gold, and score (days×10 + gold×100).

Survival
Stats: HP, food, water, energy. Decay over time; death resets the game.
Food gives small increments: coconut +8 food +6 water, small fried fish +18, big fried fish +30, raw fish +5/+8. Eating near the table adds +4.
Eating a coconut plays a smash animation: he carries it to the nearest palm, knocks it twice overhead and cracks it open (effects apply at the crack).
Coconuts: shake palms; each coconut regrows in 1–1.5 days. Start with 2.
Fresh-water spring on the east side of the island.
Campfire burns out after one day (flame shrinks as fuel drops, burns down overnight when sleeping) and must be rebuilt with wood.
Sleep at the campfire at night to restore energy and skip to morning.
Gathering
Flotsam drifts by (driftwood, rope, crates, message bottles with funny notes, rarely a telescope) — swim out to collect.
Treasure: X marks appear in the sand; dig 3 times for rocks (common, needed for tools), gold, rope, wood, a telescope, or an old boot.
Fishing: the spear is THROWN in an arc into the shallows and bobs upright ("PULL SPEAR" to catch small fish); the rod casts a line with a bobber for big fish. Fry either on the campfire.
After the little hut is built, the axe can CHOP the three palm trees: swing animation, then the palm topples over with a thud and leaves a stump (+6 wood, and no more coconuts from that tree).
Building (B menu; locked items show their requirement)
CAMPFIRE (2w) — always available; burns out daily.
MAKESHIFT HAMMER (1 rock + 1 rope) and MAKESHIFT AXE (1 rock + 2 rope) — both available from the start, build in either order.
FISHING SPEAR (1w+1r) — needs axe.
COVER (4w+2r) — needs hammer AND axe. Shelters from rain; "SIT UNDER COVER".
CHAIR (2w+1r) — needs cover; he visibly sits on it.
TABLE (3w+1r) — needs chair; +4 food when eating nearby.
FISHING ROD (2w+2r) — needs axe + table; catches big fish.
LITTLE HUT (6w+3r) — needs cover; "SIT IN HUT" in the doorway; unlocks palm chopping.
MAST (2w+1r) — needs little hut.
SAILS (3 parachutes + needle&thread) — needs mast.
RAFT (8w + 5r + 4 coconuts for flotation) — needs sails; SAIL AWAY.
Hazards & events
Shark: patrols beyond a deep-water boundary; swim too far and it chases and eats you (reset). It also periodically swims up to the shore for a "friendly" chat, inviting the castaway for a swim (speech bubbles).
Seagulls: periodically fly in to steal fish (never coconuts); scare them by approaching or tapping them.
Storms roll in visibly from the west or east: the cloud bank slides across, rain/darkness/thunder ramp up with it, then it fades out. Rain drains energy unless sheltered; the castaway grumbles weather-specific lines.
Rescue plane: flies over occasionally and usually parachutes a crate onto the island — always +2 wood and +1 parachute (sail material), plus a random surprise (sewing needle & thread, rope, tinned coconut, or nothing, for a laugh). Sometimes it just flies past.
Mermaid: visits the shore now and then; approach to receive a gift.
Ships pass on the horizon; view them with the telescope (T).
The castaway mumbles funny lines with grunt sounds.
Verification
Tested in the preview browser 2026-07-05 (v3): sun/moon rise-set handoff, storm roll-in, spear throw/pull, revised build gating (hammer/axe parallel, rod after table, raft coconut cost), coconut smash timing, cover/hut sitting, island-1 → island-2 wreck arrival with inventory wipe, island-2 → WIN screen ("Survived N days across 2 islands"), win restart, palm topple animation, pause freeze/resume, plus multi-game-day soak tests of update/draw with no console errors.
