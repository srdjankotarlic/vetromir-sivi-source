# VETROMIR 7.25 / Build 43: QA Scope

September 12, 2026. Native Swift + SpriteKit, Apple Silicon, English and Serbian.
This report describes automated coverage, not a claim of a bug-free game.

## Functional Gates

- Debug and release builds, application smoke and strict ad-hoc signature checks.
- Profile persistence/recovery/reset, remapped controls, audio settings and scores.
- Ten chapters plus the final arena: all relic guardians and 16 enemy species;
  stable traversal routes, checkpoints and encounter distribution.
- 949 gameplay checks and 1,457 arsenal checks across eight heroes and
  30/60/120 simulation steps per second, including pause, input buffering,
  cooldowns, death, movement and damage routing.
- Eleven boss identities, progressive health, phase floors, adaptive attack
  choices, nonrepeating openings and bounded summon counts.
- Enemy motion/tactics, obstacles, visual rigs, loot and relic locks.
- 807 translation entries with no duplicate source entries; English boss
  combo warnings, player names and repeated-label caching are checked.
- All eleven boss arenas passed eight-second Full HD combat probes, including
  the final phase of each boss. 102 fresh SR/EN scene captures completed;
  the English capture log contains no missing-translation warnings.
- ZIP archive integrity and DMG checksums passed. The Desktop application
  matches the packaged application and passes strict code-signature validation.

## Encounter Counts

| Chapter | Ordinary enemies | Largest gap (world units) |
| --- | ---: | ---: |
| I | 78 | 1013 |
| II | 88 | 873 |
| III | 86 | 990 |
| IV | 89 | 913 |
| V | 90 | 932 |
| VI | 93 | 1130 |
| VII | 95 | 803 |
| VIII | 98 | 898 |
| IX | 99 | 1067 |
| X | 102 | 975 |

Total: 918. Each level's least-populated quarter contains at least 80% of
the enemies in its most-populated quarter. The final arena uses boss summons
instead of ordinary level population. Ordinary enemy HP remains four times
the pre-7.24 value after difficulty/co-op scaling.

## Full HD Performance

Tests use SpriteKit + Metal rendering at 1920 x 1080 on an Apple M1 Pro.
Eight separate eight-second movement/attack/loot probes averaged 59.1-59.6
update frames/s. The extended 20-second fifth-phase Nedah test averaged
59.5/s with no player death or switch to the defeat screen.

The extended test exposed a one-time initial summon stall. Preparing the
initial minions during loading reduced the largest measured simulation step
in the repeated test from 107.7 ms to 8.6 ms. This is one before/after scenario,
not a promise about every frame or device. Rendering and OS scheduling still
produce occasional longer frames.

Gates remain at least 55 average update frames/s, total game-logic CPU p95
under 6 ms and individual systems under 4 ms. Instrumentation additionally
records real SpriteKit simulation, render encoding, GPU work and wait time.
The old separate snapshot measurement is not treated as frame time.

Endurance probes use an explicit QA-only large health reserve to keep combat
active. Contacts, knockback, physics, attacks and cooldowns remain active.
This option requires a performance command and does not change normal games.
The performance gate rejects runs that finish on a defeat or victory screen.

## Limits

Not a full manual campaign playthrough for every hero, difficulty and co-op
combination. No testing on other Mac models, and no new mobile release.
The first ten boss base HP values are 525-3075; Nedah is 15751. This is a
deliberately harder balance, not a guarantee of equal difficulty for all players.
The app is ad-hoc signed and intentionally not Apple-notarized.

Report reproducible problems with your Mac model, macOS version, hero,
chapter, difficulty and a screenshot or short recording. Do not include
private profile data. [Issue tracker](https://github.com/srdjankotarlic/vetromir-sivi-source/issues).
