# Vault of Mirrors: A Le Brun Legacy
### Full build spec for Fable 5 (Claude Code session)

## Premise
Beneath the real Hall of Mirrors at Versailles — designed by Charles Le Brun, First Painter to Louis XIV — lies a hidden vault. Centuries ago, Le Brun didn't just paint the ceiling: he secretly bound powerful beings into enchanted mirror-frames to protect France, sealing each one as a "First Appearance." The player is a modern Le Brun descendant who has just inherited the vault key and must descend through it.

This is a **roguelike deckbuilder** (Slay the Spire structure): procedurally generated floors, a growing deck built mid-run, permadeath per run, permanent meta-progression unlocks between runs. Single self-contained HTML file, Canvas/DOM based (no external engine needed) — matches the existing pipeline.

## Core hook: the grading mechanic
Every card is a "First Appearance" — a character pulled into play. Cards drop with a random **CGC-style grade** (2.5 to 9.8) that scales their power:
- **Higher grade** (8.0–9.8): stronger stats, but rarer to find and costs more of the run's limited "restoration" resource to keep in your deck at full power
- **Mid grade** (4.0–7.0): the workhorse tier — reliable, efficient, cheap to maintain. This should be the statistically best value tier by design, mirroring the real-world collecting philosophy of budget-conscious mid-grade over expensive high-grade
- **Low grade** (2.5–3.5): cheap filler, high risk/reward — a damaged card might have a random negative quirk alongside strong stats

Grade should visually show on the card as wear/scratches/a corner-tear effect at low grade, cleaning up to pristine at high grade.

## Card roster
Source characters (Higgsfield-generated portraits — user will supply image files, same workflow as the life-sim project):

**Standard cards (mid-tier roster):** Spider, Deadpool, Scarlet Witch, Cloud, Tifa, Nathan, Cadet, Magnolia, Enforcer, Veil, Spiderdemon, Tornada, Darkhold, Silverflash, Ant
**Basic/common cards:** the numbered set — One, Two, Three, Four, Five — as low-cost/low-power starter guardians
**Boss:** **Zorr** — the corrupted revenant, dark warrior with ashen cracked skin and a corroded warhammer, is the escalating final boss across the run, appearing corrupted-and-strengthening at each major floor transition before the true final confrontation
**Curators (life-sim crossover cameo):** Nico, Jorge, Sophia, Gabby, Mateo, Laurent appear as shopkeepers/blessing-givers between floors — each offers a themed service matching their life-sim career (e.g. Sophia offers a finance-themed resource-doubling wager, Jorge offers a "contract" that removes a bad card from your deck, Nico offers a card upgrade "remix," Laurent offers a defensive buff, Gabby & Mateo offer a whimsical double-or-nothing card duplication, playing on their acting/dream-selling personalities)

## Floors (procedurally generated, themed after real Versailles rooms)
1. **The Gardens** — tutorial floor, easiest enemies
2. **Peace Salon**
3. **War Salon**
4. **King's Apartments**
5. **Hall of Mirrors** — the final gauntlet leading to Zorr

Each floor: a branching node map (combat nodes, curator/shop nodes, rest nodes, event/story nodes, one boss node at the end).

## Combat
Turn-based card combat, single player character (the Le Brun descendant) vs enemies drawn from the roster acting as hostile mirror-corrupted duplicates on the way down, escalating in stat totals per floor. Standard deckbuilder resource: an energy/action-point pool per turn. Cards have attack, defend, and utility/buff types.

## Meta-progression (between runs)
- Permanent unlocks: new cards enter the draft pool as the player finds them in runs
- A "Restoration Ledger" tracking best runs, fastest clears, and a collection log styled like a CGC census/registry — a direct nod to the real-world collecting hobby
- Difficulty modifiers unlockable after first clear (a "Signature Series" hard mode, styled after signed/rare book variants)

## Visual style
Painterly/illustrated card frames evoking real comic slabs (label, grade sticker, holo border for the boss/curator cards). Environment art: moody, gilded, candlelit Versailles interiors — consistent with the tone of the existing Hall of Mirrors Three.js project, but rendered in 2D/illustrated style here, not 3D.

## Technical notes
- Single HTML file, Canvas-rendered combat + DOM-based menus/cards
- Save state via localStorage-equivalent in-memory pattern already used in this pipeline (no external storage dependency)
- Structure the build in clear phases and commit after each: (1) core combat engine + basic 5 cards, (2) full card roster + grading system, (3) procedural floor/node map generation, (4) curators + shop system, (5) Zorr boss encounter + escalation, (6) meta-progression/unlock system + polish pass
- This is a large, multi-system build — expected to run long. Prioritize getting a fully playable core loop (floors 1–2, basic combat, a handful of cards) working early, then layer in the rest of the roster and systems on top

## Assets needed from user (not blocking — can build with placeholders first)
Character portrait image files for: Spider, Deadpool, Scarlet Witch, Cloud, Tifa, Nathan, Cadet, Magnolia, Enforcer, Veil, Spiderdemon, Tornada, Darkhold, Silverflash, Ant, One–Five, Zorr, Nico, Jorge, Sophia, Gabby, Mateo, Laurent. Build with clean placeholder card frames (colored silhouette + name) first so the game is playable immediately; swap in real portraits as they're supplied.
