# Evidencija asseta

## Verzija 7.4

### Licenca

Četiri muzička izvora preuzeta su 28. avgusta 2026. sa Pixabay-a pod
[Pixabay Content License](https://pixabay.com/service/license-summary/). Licenca
dozvoljava korišćenje, preradu i komercijalnu upotrebu kada je sadržaj ugrađen u
veće kreativno delo kao što je igra. Nije dozvoljena samostalna redistribucija
izvornog audio fajla.

Originalni MP3 fajlovi se ne distribuiraju. U igru ulaze uređene AAC petlje i kratki
PCM akcenti, povezani sa originalnim proceduralnim miksom, kontrolama jačine,
duckingom i limiterom. Kredit nije obavezan licencom, ali je namerno naveden.

### Izvori

| Delo | Autor | Pixabay izvor | Izvorni SHA-256 | Upotreba |
|---|---|---|---|---|
| Monastic Folk Drone 2 | pietiX | https://pixabay.com/music/folk-monastic-folk-drone-2-535377/ | `bee9dfbb31ef866e8d019a81b6287b3c28c77f269b923b3219ac0bb290ba38eb` | pohod, najava čuvara |
| Cinematic Celtic Fog 1 | pietiX | https://pixabay.com/music/orchestral-cinematic-celtic-fog-1-562124/ | `019cc95f263a1e8f9044261ec0748cf4b4988aab4b2eb0ff223741c521da4bda` | meni, zastava |
| Cinematic Homecoming Dramatic | pietiX | https://pixabay.com/music/orchestral-cinematic-homecoming-dramatic-587436/ | `6cc5a9ae262fa8f6a87a7cf2752ebd5c0f05f4d1a582a6edaeefe87ccd9d2d3a` | pobeda, epilog, lični potez |
| Arabischer Tanz, Mittelaltermusik nach einer spanischen Cantigas | VictorvanTast | https://pixabay.com/de/music/moderne-klassische-arabischer-tanz-mittelaltermusik-nach-einer-spanischen-cantigas-137674/ | `6d053b7c52a45544188c2e94dfdef43ae3e06fe4251082f9d23ab57f6601f355` | borba sa čuvarom, potvrda |

Pixabay stranice označavaju tri pietiX izvora kao AI-generisana. Materijal nije
korišćen za obuku modela; samo je audio-montažom ugrađen u ovu konkretnu igru.

### Izvedeni fajlovi

- `menu_celtic_fog.m4a` — `d35dae7240e176c68bd6f09d2df443f9fe40cf4d7624e481d0dc868dc417013c`
- `level_monastic_drone.m4a` — `3ee0bec68a54b8d26e185dd2fb9c8c6280e18ac4d0cebd03a8476608fb2d2fc4`
- `boss_cantiga_dance.m4a` — `a7a6134f2daac7fa67f6f25a9caf733c1fc7038affa34155a68ba2781c63fd15`
- `victory_homecoming.m4a` — `a3374a8122d9b23c7f62490e7709ba9707fb8c8fbe211ebb6863fa2498bca967`
- `accent_ui_confirm.caf` — `9556fdd8c725ecc6390cdc8fc6724f7d25eb6996af6534f091168b58dc477548`
- `accent_checkpoint.caf` — `64165c5e39258e39aa7c6b822007285b9b9034adfc5adea36347358da279a00a`
- `accent_signature.caf` — `005de96fbfffedd9d0b474378984d8a63f4e0311ad88efd83fb1d4195dd10c6b`
- `accent_boss_omen.caf` — `8a9503fce90a0d6d44abc96ee26d381c91f38451a81593ae1fa9acf91cf1c17a`
- `accent_victory.caf` — `157f0551cdc196fe2feecf1e8030f8746be64f812437e38f8a97cc4c60ddbe24`

Petlje su ukrštene na završetku, normalizovane i filtrirane. Akcenti su kratki,
dodatno stišani i ne mogu zameniti ili rekonstruisati pune izvorne kompozicije.

### Projektni asseti

- `AppIcon.icns`: generiše `scripts/makeicon.swift`; originalni projektni rad.
- Grafika i teksture: proceduralno generisane u `Sources/Vetromir/`.
- Borbeni zvučni sloj: sintetizovan u `Sources/Vetromir/Audio.swift`.
- Avenir Next i Baskerville: sistemski macOS fontovi; ne distribuiraju se kao fajl igre.

Svaki budući spoljni asset mora dobiti naziv autora, izvorni URL, tačnu licencu,
datum preuzimanja i spisak izmenjenih fajlova u ovom dokumentu.

## Promotivni materijal

Folder `marketing/` nije deo aplikacionog paketa. Naslovne ilustracije nastale su
28. avgusta 2026. u AI-podržanom procesu koristeći isključivo projektne capture
kadrove kao vizuelnu referencu. Završni logo, tipografija, formati prodavnica,
promotivne kartice i trejler sastavljeni su projektnim skriptama. Dva izvorna
gameplay snimka dostavio je vlasnik projekta i koriste se samo za promociju igre.
