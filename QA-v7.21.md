# VETROMIR 7.21: Tested Scope

Build 39, September 10, 2026. Native macOS Apple Silicon, English and Serbian.

## Release Gates

- Debug and optimized release builds passed. The packaged app and Desktop copy
  passed startup smoke checks in both languages.
- Arsenal regression: **1,086 assertions**, all eight heroes, all four found
  attacks, at 30/60/120 simulation steps per second.
- Gameplay regression: **853 assertions**, including input, movement, hit-stop
  and pause handling.
- Profile compatibility, campaign, hero identities, journey, signatures, motion,
  bosses, audio buffers, enemy motion/tactics, obstacles and adventure checks passed.
- Localization: **796 entries, zero duplicates**. All 51 deterministic capture
  scenes were generated in both languages, **102 Full HD captures** total; the
  English capture pass reported no missing localization keys.
- All 48 approved cartoon-art file hashes matched. Release audio files were
  checked against the asset-credit inventory.
- ZIP integrity, DMG checksum verification and ad-hoc code-signature validation
  passed. `SHA256SUMS-v7.21.txt` identifies the two installer files.

New attack coverage includes actual damage through the central damage functions,
cooldowns and mana, held-button suppression, buffered taps, restoring the fourth
skill slot, real enemy-drop collection, death cleanup and pause-frozen timers.
Additional cases cover scissor anticipation and single hits, mine/platform support,
one-way surfaces, and reflecting projectiles with a ground-level mirror.

## Performance Probes

Test machine: Apple M1 Pro MacBook Pro, connected to power. All visible game
probes used only **Built-in Retina Display**, without sound or focus activation.

The final release run sampled 11 campaign/checkpoint scenes. Script CPU update
p95 ranged from **1.944 to 4.375 ms**. Average scene-update cadence was
**59.7 to 59.9 updates/second**. Three additional eight-second movement-and-arsenal
probes passed with Gvozdan, Vukasin and Rujana; all averaged 59.8 updates/second,
with CPU p95 of 2.840, 1.309 and 1.487 ms respectively.

The former 2.5 ms CPU gate failed during earlier candidate runs. Face and surface
deformation now cache invariant calculations; a parity test checks the cached
surface result against the reference formula to within 0.000001. The desktop
gate was explicitly revised to **6 ms total CPU p95**, **4 ms per subsystem p95**,
and a minimum average cadence of **55 updates/second**. These are budgets within
a 16.67 ms 60 Hz frame, not a claim that every frame takes only 6 ms.

These readings measure the instrumented CPU update and callback cadence, **not
GPU presentation latency**. The diagnostic frame-capture/readback cost is excluded
from normal gameplay timing. Scripted movement probes inject loot to exercise
the arsenal; natural drops are covered separately by the integration assertions.

## Limitations

This is not an exhaustive human playthrough of every hero, difficulty, co-op
combination and chapter. Deterministic captures are staged QA scenes, not proof
that each scene was reached in a continuous playthrough. Selected screenshots
were visually reviewed; not every animation frame was manually inspected.

No broad Mac hardware matrix, iPhone/iPad update, Intel port or Apple notarization
is included. Quiet tests validate audio data and playback paths, not a fresh
subjective listening review. No claim of zero bugs or identical performance on
every Mac is made.

Report reproducible issues with the build, Mac model, chapter, hero and steps in
[GitHub Issues](https://github.com/srdjankotarlic/vetromir-sivi-source/issues).
Do not attach private profile data without reviewing it first.
