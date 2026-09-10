# VETROMIR za iPhone

> Arhiva izdanja 7.7. Aktuelna verzija 7.21 je samo za Mac; ovaj paket nije ažuriran.

Verzija 7.7 koristi isti SpriteKit gameplay, kampanju, balans, zvuk i proceduralnu
grafiku kao macOS igra. Mobilno izdanje nije uprošćena web kopija: svih deset
poglavlja, Nulto nebo, osam junaka, rang-lista, oprema, priča i lokalni co-op ostaju.

## Jezik

Postoji jedna dvojezična iPhone aplikacija sa srpskim i engleskim jezikom. Pri prvom
pokretanju prati jezik uređaja; kasnije se jezik menja u **MOBILNI ZVUK I KONTROLE**.
Promena jezika ne briše napredak. Mobilni profil je odvojen od macOS profila.

## Kontrole na dodir

| Kontrola | Radnja |
|---|---|
| Plutajući joystick | kretanje; povlačenje nadole koristi komandu dole |
| Munja | osnovno oružje; prevuci od dugmeta da usmeriš nišan |
| Strelica nagore | skok i pariranje odgovarajućih projektila |
| Vetar | nalet izabranog junaka |
| Obojena ikona moći | dodir koristi izabranu moć; na iPhone-u prevlačenje bira sledeću |
| Pauza | otvara meni pauze |

Pauza i džojstik su u levoj crnoj traci, a moć/nalet i skok/napad čine
dva para u desnoj traci, izvan zone kamere i senzora. Nijedna kontrola ne prekriva teren. Kontrole podržavaju
više istovremenih dodira. U mobilnim podešavanjima mogu da se
ogledaju za levu ruku, povećaju ili smanje, učine providnijim i da im se isključi
vibracija. Safe area štiti dugmad od notch-a i home-indicatora. SpriteKit scena koristi
`aspectFit`, pa ceo kadar ostaje vidljiv na različitim iPhone ekranima.

Ekran upravlja prvim igračem. Drugi lokalni igrač se pridružuje zasebnim Bluetooth
kontrolerom na izboru junaka. Igra se koristi vodoravno.

## Podržani uređaji

- iOS 15 ili noviji
- iPhone sa arm64 procesorom i Metal podrškom
- preporuka za pun efekat: iPhone 11 ili noviji
- opciono kompatibilan Bluetooth kontroler

## Provera bez Xcode-a

```bash
cd "$HOME/Documents/VIBE KODIRANJE/vetromir"
./scripts/validate-mobile-project.sh
```

Kapija proverava plist, storyboard, JSON katalog ikona, dimenzije i alfa kanal svih
osam iPhone ikona, prisustvo svakog runtime Swift fajla u targetu i kompajlerski
proverava svih 36 mobilnih izvora. Očekivano se završava sa
`MOBILE-PROJECT-OK iphone=1 ipad=0`.

## Build u Xcode-u

Za stvaran simulator i uređaj potreban je puni Xcode. Za App Store Connect upload od
28. aprila 2026. potreban je Xcode 26 ili noviji sa iOS 26 SDK-om i Apple nalog.
Simulator i nepotpisani build za fizički uređaj proveravaju se na ovom razvojnom Macu.

1. Instaliraj Xcode iz Mac App Store-a.
2. Aktiviraj ga: `sudo xcode-select -s /Applications/Xcode.app/Contents/Developer`.
3. Otvori `VetromirMobile.xcodeproj` i target **Vetromir Mobile**.
4. U **Signing & Capabilities** izaberi svoj Team i po potrebi promeni bundle ID.
5. Izaberi iPhone simulator ili priključen iPhone i pritisni Run.

Build simulatora iz Terminala:

```bash
./build-mobile.sh simulator
```

Arhiva za distribuciju:

```bash
VETROMIR_DEVELOPMENT_TEAM=TV0J_TEAM_ID ./build-mobile.sh archive
```

Arhiva nastaje u `dist/Vetromir-Mobile-7.7.xcarchive`. Za TestFlight u Xcode
Organizer-u izaberi **Distribute App → TestFlight & App Store**. Apple zahteva članstvo
u Apple Developer Program-u za TestFlight i javnu App Store distribuciju.

`Mobile/PrivacyInfo.xcprivacy` prijavljuje da igra ne prati niti prikuplja podatke.
Deklariše samo lokalni `UserDefaults` izbor jezika (`CA92.1`) i sistemski monotoni sat
za audio tajmere (`35F9.1`); nijedan od tih podataka se ne šalje sa uređaja.

Zvanična Apple uputstva:

- https://developer.apple.com/documentation/xcode/distributing-your-app-for-beta-testing-and-releases
- https://developer.apple.com/testflight/
