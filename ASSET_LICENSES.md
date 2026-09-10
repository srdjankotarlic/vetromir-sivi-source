# Evidencija asseta

## Desktop 7.15: Krivudavi vetar (aktivni izbor)

Korisnik je zatražio originalni crtani fantasy umesto ozbiljnog slikanog smera.
Svih 48 aktivnih PNG-ova u `Resources/Art` zamenjeno je novim originalnim
ImageGen izlazima: osam junaka, 16 neprijatelja, 11 bosova, sedam pozadina,
četiri lista scenografije i dva lista predmeta. Generisano 8. septembra 2026.
bez ulaznih slika drugih igara ili filmskih likova. Ovo je AI-assisted art,
ne CC0 paket, kupljena ilustracija niti tvrdnja o ljudskom ručnom slikanju.

Merodavni brief, puni promptovi, izbori između pokušaja i SHA-256 manifest su
u `Resources/Art/Cartoon-7.15/`: `BRIEF.md`, `Cast.md`, `Bestiary.md`,
`Bosses.md`, `World.md` i `SHA256SUMS`. Originalni PNG-ovi nisu precrtavani,
preskalirani ili kolor-korigovani posle generisanja. Atlas-i su 1536 x 1024,
a pozadine 1672 x 941 (frost 1672 x 940); ne oglašavati izvore kao 4K.

Animacioni atlas-i imaju stvarni alpha kanal i šest delova. Stroga margina
32 px nije svuda ispunjena: runtime ignoriše alpha <= 8 i izdvaja povezane
delove u memoriji. Za vrh krila moon, plašt gromoplam i trozubac vihorad
postoje eksplicitno prošireni izvorni prozori. Sitne zadnje šake crtaju se
u Swift-u preko otvora rukava. To su operacije renderer-a, ne izmene originala.

Sledeći odeljci su istorija prethodnih izdanja. Njihovi hash-evi više ne
opisuju aktuelne fajlove i ne predstavljaju dodatne assete u aplikaciji.

## Desktop 7.14: Bronzani vetar

Dva originalna ImageGen lista, generisana 8. septembra 2026. bez referentnih
slika drugih igara. AI-assisted art, ne CC0 paket niti tvrdnja o ljudskom ručnom
slikanju. Originalni RGBA PNG-ovi su neizmenjeni, po 1536 x 1024 piksela.
Stroga tražena margina nije potpuno ispunjena: postoje alpha=1 tačke, a trgovac
i fenjer imaju donju marginu 21–24 px. Svi stvarni oblici staju u svoja polja.
Postojeća runtime alpha izolacija odstranjuje zanemarljive tačke, ne boju predmeta.
Brief: `Resources/Art/Wayfarer/PROMPTS.md`. Puni promptovi i odbačeni pokušaji:
`output/v7.14-qa/camp-generation.md`, `output/v7.14-qa/relics-generation.md`.

| Fajl u Resources/Art | SHA-256 |
|---|---|
| `Wayfarer/camp.png` | `52173574aee34f08b3ef5733ee9f62279e0348b2c895ad5b9b7399492c4df710` |
| `Wayfarer/relics.png` | `0d91d455e5aa01f7889add84bfd9524de85eb7e0076ea47fcb17279b789691c1` |

## Desktop 7.13: bestijarijum i prednji plan

27 modularnih protivnika i četiri lista scenografije generisani su 8. septembra
2026. ugrađenim OpenAI ImageGen alatom. Originalni briefovi, bez ulaznih slika
tuđih igara/filmova. Nisu CC0 pack niti ljudski ručni rad. Distribucija je u okviru
iste projektne politike kao za junake 7.12. Svi PNG-ovi: 1536 x 1024, šest zasebnih
delova i pravi alpha kanal. Konačni fajlovi su neizmenjene kopije izlaza alata.
Izdvajanje alpha-komponenti i ogledanje tla obavljaju se u memoriji pri prikazu.

Brief i pravila: `Resources/Art/Bestiary/PROMPTS.md` i `Resources/Art/Scenery/PROMPTS.md`.
Detaljni radni dnevnici sa originalnim putanjama i neuspelim pokušajima:
`output/v7.13-qa/{scavengers,wardens,ancients,sovereigns}-generation.md`.

| Fajl u Resources/Art | SHA-256 |
|---|---|
| `Bestiary/barjaktar.png` | `d2d39b150275b49b8737f46ca33ed64deb4df462bbc84b409dec6354299e2ab6` |
| `Bestiary/bastion.png` | `9490e8b7035950a758c5de5945158d3953c38507e1868df21b94458ba0910c88` |
| `Bestiary/bezimeni.png` | `cf9ddba5176ebd3a01e6ea13c0640e495dc3dfc929ca0ea7c47892cae38158b4` |
| `Bestiary/burrow.png` | `bded747f3d5f6cc87e05b376e6589158ae1c0d6e0db92fb8d5da6a4ecb048717` |
| `Bestiary/chain.png` | `43a607e0b5826ecefe885f44faecdca0e2fa13d48e77f5cd83746fb9df34cb22` |
| `Bestiary/cinder.png` | `3c391cae7159ea963d094f5c12a9900bd02c72929c8d5db17b6af92840536d88` |
| `Bestiary/echo.png` | `ad8ccd91f3b3f06607d346da5d9c661de39f57d2160eff600f8bdef65b114a58` |
| `Bestiary/gromoplam.png` | `edbdb8b55f8f8b55fc8f834d8fd92a7e36e2ac43ead579150fc27756ba41a0dc` |
| `Bestiary/hunter.png` | `71ccf9af356d6389772c63ee4fea78aa59061c90d7c879a19ba888744f0731e0` |
| `Bestiary/kamenovid.png` | `3312f555b1341987c5a9e5d20e7bc179e55eef5561d13e576138bbcf54892cd7` |
| `Bestiary/krilolom.png` | `35213a36bc8863e09abf1d3bbf38f3a55298d4249caaa450493de004f9beb439` |
| `Bestiary/lantern.png` | `34ba512e1ca51765ac8f5c109afe6d5466137ad12f60fe6e9744e720ae43432c` |
| `Bestiary/mirror.png` | `5596f79c14d11a0a986b173dc277fea00c87bfade2d1240e2a50adffca9dd563` |
| `Bestiary/moon.png` | `69ebe2e6d530d9fb626008dc61ff9ad4e92539d1cc2ec1a73f326b383535cbca` |
| `Bestiary/mraznik.png` | `e1c42b465b590540fcd7a9661f9117e0a6f9f682fc94644653b7ce5e94866cbe` |
| `Bestiary/nedah.png` | `9a419f461029797c6e9ebd0d56e8548d3655a1111d5f102f09fbf02530c4dbf7` |
| `Bestiary/raider.png` | `fe55514b7fc10aa3bee9ce145e373d1c19b7672a1ebbf6e90d5a28a6692c4416` |
| `Bestiary/root.png` | `04eedcb7014bd35e551d90e8118b6d98ae3aa606c116e60e21d9c9001f377ffe` |
| `Bestiary/spark.png` | `b1d817df287abb04536af407c1c5b62f679d55d0844a273c4275d601a94024ff` |
| `Bestiary/spore.png` | `778b9ba58fce56138f3a024af04eb8288936c46a80c4954ac4ea9b96b4cf5b0c` |
| `Bestiary/storm.png` | `e040aab3404546181e9032312ea362bff2a7552a8872c72ee09a9007c4d2f1a6` |
| `Bestiary/thornback.png` | `1389cf6c0fa2e46e94d672c53b116797307e62c0e1bdbacc8414639918db7aa6` |
| `Bestiary/tihomor.png` | `f0072d141ec1533ea8b637335fb0ceb7dfbf3733868a09142521cbfcf0668db5` |
| `Bestiary/uzvodnik.png` | `4ea0a7a90dbf4e7ac995d9657e986458c8ab390a95adcfde343d8b70ae111a00` |
| `Bestiary/vihorad.png` | `80b2de88f65411f37d86259cb8e1e5d6b5e89bc627a0df6bd97a48f0afc5beeb` |
| `Bestiary/ward.png` | `ddff18b5cfaa8e96f6df2e3757d5cf128648da12cf65a7905516a4147ed56aa7` |
| `Bestiary/zvonozder.png` | `c5f80f1ee5dd97a1d0ececbddbf67dd4cdbf1adf15fddfc8cd04d41955576c75` |
| `Scenery/ember.png` | `957c5e2161523752bfb980f7ee29b40b6f5d043c2966b819c72f1ab513f2b419` |
| `Scenery/frost.png` | `014abfe3adfcf1147d07f4baec8461373601a19910931e8a94f9e2c49b9b5b94` |
| `Scenery/grove.png` | `0354443311acdf879ab596ebc2fa810615ddfe04fefbfe09282872c87391c34f` |
| `Scenery/ruins.png` | `ace64ed4679d4d1f0221be42ebac26358577b47ce96a7a44637d88ede5af3cd0` |

## Desktop 7.12: slikani junaci

Osam originalnih modularnih atlas-a nastalo je 8. septembra 2026. pomoću ugrađenog
OpenAI ImageGen alata u Codex-u. Konačni izvori generisani su bez ulaznih slika
tuđih igara ili filmova. Nisu predstavljeni kao ljudski ručni rad niti kao CC0
asset pack. Distribuiraju se kao sastavni deo igre prema postojećoj projektnoj
politici. Svaki PNG ima 1536 x 1024 px i stvarni alpha kanal; ceo list sadrži šest
delova, a ne jednog junaka u toj rezoluciji.

| Fajl u Resources/Art/Cast | SHA-256 |
|---|---|
| `vetromir.png` | `771d9e3dc746ad9c1a1d1aebb0d1b57b921c8c2b39e63808cc374c504fe21582` |
| `vukasin.png` | `97de16c4ebf421584f4da6730e8295aaf5bc2a239527accb21ffb4149a701078` |
| `zorvid.png` | `461a701ef2666a17a2ea63fbecaef74acf9f5fc2ea3964a2e713d08c3565d6fd` |
| `gvozdan.png` | `9b57e21f43d00459887e3cf938520ff49114d8841d561e86e9cdd0ba73801dc5` |
| `ognjen.png` | `50493e979e0f40e1aa442cb8c9ed1638f0b1d88aacd9e5d58ba73c3913ba0af6` |
| `rujana.png` | `74f2f8535af17e3b9c33c80219dd10a389e2f0cdf79f8928b5eaa3e143f50252` |
| `jasenka.png` | `263849b333ab02831315d479b7bfcf61645742affa4469a19d2924b0ee576c40` |
| `nocena.png` | `6b35397b0ab49a35fabdd1c3e8426f6c88f3de8691310a620c1acfa1f2c92eb1` |

Konačan izbor i pravila izdvajanja: `Resources/Art/Cast/PROMPTS.md`.
PNG-ovi su neizmenjene kopije generisanih izvora. Kod izdvaja delove i odvojene
alpha-komponente pri prvom učitavanju; ne prepisuje datoteke i ne menja boje kože,
tkanine ili metala. Raniji neprozirni pokušaji nisu uključeni u aplikaciju.

## Desktop 7.10: nebo, reka i završnica

Još tri originalne slike generisane su 8. septembra 2026. ugrađenim OpenAI ImageGen
alatom u Codex-u, bez ulaznih slika iz tuđih igara. Ovo je AI-podržana produkcija,
ne kupljeni asset pack niti rad predstavljen kao ručno slikan. Ista politika
porekla i distribucije kao u odeljku 7.9. Fajlovi su neizmenjene kopije izlaza,
stvarne rezolucije 1672 x 941 px; ne oglašavati ih kao 4K.

| Fajl u Resources/Art | Uloga | SHA-256 |
|---|---|---|
| `sky-painted.png` | More iznad neba | `a8c6ea756f83691e0a5e88eb5eca4bbb9906dcac11d127a5b68ebf4d391afbe3` |
| `river-painted.png` | reka koja teče naviše | `07a3f171a8aed620f0222e5afcc86f55b0b992685678dd330914a16a17c28700` |
| `void-painted.png` | poslednji prelaz i Nulto nebo | `5964645559d0e4bcd5216b1292be255f095bef475106c4e8248e00ffc32cb533` |

Kostimi, lica, maske, krila i gravure u 7.10 su projektna vektorska geometrija
napisana u Swift-u, bez preuzimanja spoljnih sprites. Briefovi i ID-jevi originala
nalaze se u `Resources/Art/PROMPTS.md`.

## Desktop 7.9: slikani pejzaži

Četiri originalne slike generisane su 8. septembra 2026. ugrađenim OpenAI ImageGen
alatom za ovaj projekat. Nisu preuzeti tuđi sprites, likovi ili slike iz igara.
Reference u ART_DIRECTION.md služe analizi kompozicije i čitljivosti, ne kao ulazne slike.
Ovo nisu kupljeni asseti niti asseti sa pripisanom CC0/CC BY licencom. Ne tvrdi se
da ih je čovek ručno naslikao. Distribuiraju se kao sastavni deo Vetromira.

Svi fajlovi imaju stvarnu rezoluciju 1672 x 941 px. Ne reklamirati ih kao 4K izvore.
Vektorski likovi, UI i teren se zasebno renderuju u rezoluciji ekrana.
Prompts i odluke su sačuvani u `Resources/Art/PROMPTS.md`.

| Fajl u Resources/Art | Uloga | SHA-256 |
|---|---|---|
| `grove-painted.png` | mesečev gaj, korenske dvorane | `ee3480d4a4f979468e8a5c2ff1ac1af30120bdb50a2788b0904df85e38d1bb8c` |
| `frost-painted.png` | ledeno svetilište i nebeski predeli | `d243599c81998bf44c5d0a454a3ca6f8026b2af2f1e9d295ea78ba586f323823` |
| `ruins-painted.png` | grad, zvonici, završna dvorana | `be2947d09f9616600fcb1df035ab9646a8884b73dd138a74798f2c31262aaeeb` |
| `ember-painted.png` | kovačnica i olujni ratni predeli | `b7ad51d59ad10e54b178887ad8a31b751521640d9ffe3bbcea6f33c3bc3129f6` |

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
- Likovi, teren i materijali: proceduralno generisani u `Sources/Vetromir/`.
  Desktop 7.9 dodatno koristi slikane pejzaže navedene iznad.
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
