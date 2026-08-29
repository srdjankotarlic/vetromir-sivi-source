# Instalacija VETROMIRA na iPhone

VETROMIR 7.7 je nativna iPhone igra za iOS 15 ili noviji. GitHub izdanje je
besplatno, ali Apple ne dozvoljava direktnu instalaciju nepotpisanog `.ipa` fajla
dodirom u Safariju. Korisnik zato jednom mora da potpiše aplikaciju svojim Apple
nalogom preko AltStore Classic-a ili Xcode-a.

## Najlakše: AltStore Classic

1. Instaliraj [AltStore Classic](https://altstore.io/) na iPhone prema zvaničnom
   AltStore uputstvu. Potreban je Mac ili Windows računar i besplatan Apple nalog.
2. Na iOS-u 16 ili novijem uključi **Settings → Privacy & Security → Developer Mode**.
3. Na iPhone-u otvori [VETROMIR AltStore izvor](altstore://source?url=https%3A%2F%2Fsrdjankotarlic.github.io%2Fvetromir-sivi%2Faltstore-source.json).
   Ako se izvor ne otvori automatski, u AltStore-u dodaj adresu
   `https://srdjankotarlic.github.io/vetromir-sivi/altstore-source.json`.
4. Izaberi **VETROMIR: SHADOWLANDS ADVENTURES** i pritisni **INSTALL**.

AltStore Classic potpisuje aplikaciju lokalno tvojim nalogom. Besplatan Personal
Team zahteva periodično osvežavanje potpisa; plaćeni Apple Developer nalog traje
duže. Igra nema oglase, kupovine, nalog, telemetriju ni mrežno prikupljanje podataka.

## Zvanično: Xcode

1. Preuzmi `Vetromir-iPhone-7.7-Xcode-Source.zip` sa
   [GitHub izdanja](https://github.com/srdjankotarlic/vetromir-sivi/releases/tag/iphone-7.7).
2. Raspakuj paket i otvori `VetromirMobile.xcodeproj` u aktuelnom Xcode-u.
3. U **Xcode → Settings → Accounts** prijavi svoj Apple nalog.
4. Izaberi target **Vetromir Mobile**, zatim **Signing & Capabilities** i svoj
   **Personal Team**. Ako Xcode traži, promeni Bundle Identifier u jedinstvenu vrednost.
5. Poveži iPhone, izaberi ga kao Run Destination i pritisni **Run**.

Ovaj put koristi isključivo Apple-ov Xcode. Besplatni Apple nalog dovoljan je za
ličnu instalaciju na sopstveni iPhone; javna instalacija jednim dodirom zahteva
App Store distribuciju i plaćeni Apple Developer Program.

---

# Installing VETROMIR on iPhone

VETROMIR 7.7 is a native iPhone game for iOS 15 or later. Apple does not allow an
unsigned `.ipa` downloaded from GitHub to install directly from Safari, so each user
must sign it once with their own Apple Account.

## Easiest: AltStore Classic

1. Install [AltStore Classic](https://altstore.io/) on the iPhone using AltStore's
   official guide. A Mac or Windows PC and a free Apple Account are required.
2. On iOS 16 or later, enable **Settings → Privacy & Security → Developer Mode**.
3. Open the [VETROMIR AltStore source](altstore://source?url=https%3A%2F%2Fsrdjankotarlic.github.io%2Fvetromir-sivi%2Faltstore-source.json)
   on the iPhone, or manually add
   `https://srdjankotarlic.github.io/vetromir-sivi/altstore-source.json` in AltStore.
4. Select **VETROMIR: SHADOWLANDS ADVENTURES** and tap **INSTALL**.

## Official: Xcode

Download `Vetromir-iPhone-7.7-Xcode-Source.zip` from the
[GitHub release](https://github.com/srdjankotarlic/vetromir-sivi/releases/tag/iphone-7.7),
open `VetromirMobile.xcodeproj`, choose your Personal Team under **Signing &
Capabilities**, select the connected iPhone and press **Run**. A free Apple Account
supports personal on-device installation; one-tap public distribution requires the
Apple Developer Program and an App Store release.
