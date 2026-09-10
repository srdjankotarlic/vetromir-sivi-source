# Installing Vetromir on Mac

## Requirements

- Apple Silicon Mac: M1, M2, M3, M4 or newer
- macOS 13 Ventura or newer
- approximately 200 MB of free space

Intel Macs, Windows, Linux, iPhone, iPad and Android are not supported by this build.

## Recommended installation

1. Download the file ending in `macOS-Apple-Silicon-Serbian-English.dmg`.
2. Open the DMG.
3. Drag `Vetromir.app` into the `Applications` shortcut.
4. Launch it from Applications.

## First launch without notarization

The free public build is ad-hoc signed but not Apple-notarized. If macOS blocks it:

1. Open `System Settings`.
2. Choose `Privacy & Security`.
3. Scroll to the Vetromir message.
4. Click `Open Anyway`, then confirm `Open`.

You only need to do this once for that downloaded build.

## Save data

Both languages use the same profile at:

```text
~/Library/Application Support/Vetromir/profile.json
```

The language can be changed from the main menu. A legacy English profile is imported
automatically only when the shared profile does not already exist.

## GitHub download choice

Use the DMG or application ZIP attached to release 7.21. The automatic GitHub
"Source code" archive contains this distribution repository's documentation,
not an installable game. You do not need Xcode or developer tools to play.
