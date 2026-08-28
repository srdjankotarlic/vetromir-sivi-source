# Installing Vetromir On Mac

## Requirements

- Apple Silicon Mac: M1, M2, M3, M4 or newer
- macOS 13 Ventura or newer
- approximately 100 MB of free space

Intel Macs, Windows, Linux, iPhone, iPad and Android are not supported by this build.

## Recommended Installation

1. Download `Vetromir-Shadowlands-Adventures-7.6-macOS-Apple-Silicon-English.dmg`.
2. Open the DMG.
3. Drag `Vetromir English.app` into the `Applications` shortcut.
4. Launch the game from Applications.

Do not download GitHub's automatic source archive if you only want to play. Use
the DMG or ZIP attached to the release.

## First Launch Without Notarization

The public build is ad-hoc signed but not Apple-notarized. If macOS blocks it:

1. Open `System Settings`.
2. Choose `Privacy & Security`.
3. Scroll to the Vetromir message.
4. Click `Open Anyway`, then confirm `Open`.

You only need to do this once for that downloaded build. Do not disable
Gatekeeper or remove system-wide security protections.

## Verify The Download

Run this command in Terminal and compare the result with `SHA256SUMS-v7.6.txt`
attached to the same release:

```bash
shasum -a 256 Vetromir-Shadowlands-Adventures-7.6-macOS-Apple-Silicon-English.dmg
```

## Save Data And Two Editions

The English edition stores its profile at:

```text
~/Library/Application Support/Vetromir-English/profile.json
```

The Serbian edition stores its profile at:

```text
~/Library/Application Support/Vetromir/profile.json
```

Both applications can be installed and played on the same Mac without
overwriting each other's progress.
