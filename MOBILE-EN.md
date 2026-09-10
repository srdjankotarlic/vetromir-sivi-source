# VETROMIR for iPhone

> Historical 7.7 documentation. The current 7.21 release is Mac-only; this package has not been updated.

Version 7.7 uses the same SpriteKit gameplay, campaign, balance, audio and procedural
art as the macOS game. The mobile build keeps all ten chapters, the Zero Sky finale,
eight heroes, leaderboards, equipment, story and local co-op.

## Language

One bilingual iPhone app contains both Serbian and English. It follows the device language
on first launch, then allows language switching in **MOBILE AUDIO & CONTROLS** without
resetting progress. Mobile saves are separate from macOS saves.

## Touch controls

| Control | Action |
|---|---|
| Floating joystick | movement and down input |
| Lightning bolt | primary weapon; drag from the button to aim |
| Up arrow | jump and compatible projectile parry |
| Wind | the selected hero's dash |
| Coloured power icon | tap to use; on iPhone, swipe to select the next extra action |
| Pause | open the pause menu |

Pause and movement occupy the left black rail; power/dash and jump/attack form two
pairs in the right rail, clear of the camera and sensors. Nothing covers the level. The layout supports
simultaneous touches, left-handed mirroring, control scale,
opacity and optional haptics. It respects notches and the home indicator. The 16:9
SpriteKit scene uses aspect-fit presentation, so gameplay is never cropped.

Touch controls player one. A second local player may join with a separate Bluetooth
controller on the hero-select screen. The game runs in landscape.

## Requirements

- iOS 15 or later
- arm64 iPhone with Metal support
- iPhone 11 or newer recommended
- optional compatible Bluetooth controller

## Validate and build

```bash
cd "$HOME/Documents/VIBE KODIRANJE/vetromir"
./scripts/validate-mobile-project.sh
./build-mobile.sh simulator
```

The validator checks the project, plist, storyboard, icon catalog, all eight opaque iPhone icon
sizes and typechecks all 36 mobile Swift sources. A real simulator/device build needs
full Xcode. App Store Connect uploads after April 28, 2026 require Xcode 26 or later
with the iOS 26 SDK. Simulator and unsigned physical-device builds are validated on
this development Mac.

Open `VetromirMobile.xcodeproj`, select the **Vetromir Mobile** target, choose your
Apple Team under **Signing & Capabilities**, then run on an iPhone or iPhone simulator.

For a signed distribution archive:

```bash
VETROMIR_DEVELOPMENT_TEAM=YOUR_TEAM_ID ./build-mobile.sh archive
```

Use Xcode Organizer and **Distribute App → TestFlight & App Store** to upload the
archive. TestFlight and public App Store distribution require Apple Developer Program
membership.

`Mobile/PrivacyInfo.xcprivacy` states that the game does not track or collect data.
It declares only app-local language preferences (`CA92.1`) and monotonic time used by
audio timers (`35F9.1`); neither value is sent off the device.

Official Apple guidance:

- https://developer.apple.com/documentation/xcode/distributing-your-app-for-beta-testing-and-releases
- https://developer.apple.com/testflight/
