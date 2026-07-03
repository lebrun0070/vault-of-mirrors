# Vault of Mirrors: A Le Brun Legacy

A roguelike deckbuilder set in a hidden vault beneath the Hall of Mirrors at Versailles.
Charles Le Brun bound guardians into enchanted mirror-frames — each sealed at its
"First Appearance" — and you, his descendant, have inherited the vault key.

**Play:** open `vault-of-mirrors.html` in any modern browser. No build step, no dependencies —
the whole game is one self-contained file (Canvas-rendered combat, DOM-based cards and menus).

Full design document: [`vault-of-mirrors-spec.md`](vault-of-mirrors-spec.md)

## Character portraits

The game is fully playable with procedural placeholder art. To swap in real portraits,
drop image files (PNG) into `assets/portraits/` next to the HTML file, named by character id:

```
assets/portraits/one.png two.png three.png four.png five.png
assets/portraits/spider.png deadpool.png scarletwitch.png cloud.png tifa.png
assets/portraits/nathan.png cadet.png magnolia.png enforcer.png veil.png
assets/portraits/spiderdemon.png tornada.png darkhold.png silverflash.png ant.png
assets/portraits/zorr.png
assets/portraits/nico.png jorge.png sophia.png gabby.png mateo.png laurent.png
```

Any missing file falls back to its placeholder silhouette automatically.

## Build phases

1. Core combat engine + the five basic guardians (One–Five)
2. Full card roster + CGC-style grading system
3. Procedural floor / node-map generation (5 Versailles floors)
4. Curators (life-sim cameo shopkeepers) + shop system
5. Zorr boss encounters + per-floor escalation
6. Meta-progression (unlocks, Restoration Ledger, Signature Series) + polish
