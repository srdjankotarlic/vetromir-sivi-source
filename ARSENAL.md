# Arsenal 7.25

Izdanje 7.25 zadržava ove tri moći i plen. Dodaje 30% neprijatelja prema
7.24 i 25% boss zdravlja, uz brži boss pritisak. Detalji su u README.md.

## Tri osnovne moći

Svaki junak odmah ima daljinski napad, bliski napad i svoj specijal, redom u
prva tri slota. Četvrti slot je samo za pokupljeni napad. Raspored je isti po
nameni za svih osam junaka, ali njihove putanje, bliske kombinacije i specijali
ostaju različiti. Stari O/R3 i SUPER ulazi sada su aliasi trećeg slota i dele
istu manu/hlađenje. Puna energija automatski daje +40% štete narednom specijalu;
Ognjenu umesto toga daje dva dodatna odbijanja. Specijal probija gard orka.
Višestruki impulsi specijala ne ponavljaju veliko zatresanje i zastoj ekrana.

## Veza napada

Potvrđeni osnovni pogodak daje jednu iskru. Najviše tri, najmanje 0,24 s
između dobitaka; rafal kroz istu grupu ne puni odmah sva tri mesta.
Iskre traju 2,4 s od poslednjeg prihvaćenog pogotka i vide se na dugmetu
specijala u trećem slotu. Svaka iskra daje
8% više štete narednom sporednom napadu (maksimum 24%). Ognjen dobija +1
odbijanje ako ima bar jednu iskru, +2 sa tri; trajanje raste za 0,12 s po iskri.
Sporedni napad troši iskre, ali sam ne puni novu vezu. Punjenja plena su odvojena.
Pauza i hit-stop ne troše ovaj simulacioni tajmer; smrt/nov nivo brišu vezu.

Vukašin, Rujana i Noćena svojim sporednim napadom ranije pozivaju već ispaljena
sečiva. Poziv ne menja proteklo vreme projektila, broj pogodaka ni razmak
između njih. Blokiranje projektila više nije izvor mane i super energije.

Mali hit-stop traje najviše 45 ms i ima razmak od 180 ms; snažni udari i smrt
bossa ostaju zasebni. Animacija okreta ne blokira ulaz, a mesto ispaljivanja
uzima novi smer čak i pre nego što renderer nacrta sledeću pozu.

Radnja unapređuje tri osnovne moći i opremu. Stari zapisi kupljenih veština
ostaju sačuvani radi kompatibilnosti; više nisu dodatni aktivni slotovi.

| Junak | Osnovno oružje | Sporedni napad |
| --- | --- | --- |
| Vetromir | Štap spiralnog vetra: odmah otpušta usmerenu spiralu | Džepna oluja: vrtlog privlači i usporava mete |
| Vukašin | Sablja povratnog reza: jedno sečivo leti i vraća se u ruku | Ukršteni rez: najava 0,16 s, pa jedan pogodak po meti |
| Zorvid | Zvezdani luk: sidro nastaje na pogotku ili kraju leta od 380 jedinica | Prelom sazvežđa: povezuje i troši do tri sidra |
| Gvozdan | Čekić užarenog jezgra: đule u niskom luku; promašaj ostavlja minu | Crveno dugme: trenutno detonira postavljene mine |
| Ognjen | Koplje svitanja: leteće sunčano koplje, proverljiv pogodak na 480 jedinica | Ogledalo podneva: 2,4 s odbrane, četiri odbijanja pre bonusa |
| Rujana | Rapir ružinih latica: naizmenični povratni lukovi lepeze, oslonac na pogotku | Razboj svile: žičana zamka udara u tri odvojena takta |
| Jasenka | Štap živog trna: projektil na pogotku klija u kratkotrajnog stražara | Rascvetavanje: do tri izdanka se troše u rafalu latica |
| Noćena | Srp mesečevog odjeka: povratno sečivo pamti tri mesta pogotka | Još jednom juče: odloženi udari na zapamćenim mestima |

Ako nema postavljenih naprava, Zorvid/Rujana/Noćena koriste trenutni nišan,
Gvozdan kratak krug oko sebe, a Jasenka jedan rafal sa štapa. Nema besplatne
teleportacije, beskonačne zaštite niti menjanja fizičkih dimenzija junaka.
Prethodne terenske moći privremeno koriste svoje postojeće obrasce oružja.
Mine sleću na prolazne platforme samo odozgo, a od čvrstog zida se odbijaju.
Nit Rujane ostaje vezana za život zamke i ne nestaje dok je igra pauzirana.

## Plen

Drugi poraženi običan neprijatelj daje prvi osvojivi napad. Zatim svaki četvrti
sledeći daje novi. Prizvani boss podanici ne daju ovaj plen. Četiri vrste se
smenjuju; brojač pripada igraču u tekućem nivou i ne resetuje se oživljavanjem.
Plen pluta ka živom igraču u blizini i nestaje nakon 24 s. U svetu mogu biti
najviše tri neuzeta predmeta ove vrste.

- Češalj kometa: tri najavljena vertikalna udara; tri upotrebe.
- Satni kliker: usporavanje i privlačenje, zatim eksplozija; tri upotrebe.
- Kutija ogledala: odbijanje đuladi i šest krhotina; tri upotrebe.
- Kocka groma: tri odskoka sa udarnim krugovima; dve upotrebe.

Preuzeti napad zauzima samo privremeni prikaz četvrtog slota. Pritisni taster
prikazan ispod njega, po svojim podešavanjima kontrola. HUD prikazuje ime i
broj punjenja. Novi predmet zamenjuje prethodni plen. Hlađenje je 1,4 s i
zamena predmeta ga ne preskače. Poslednje punjenje ostavlja četvrti slot prazan;
držano dugme se mora otpustiti pre korišćenja novog plena. Smrt i završetak
nivoa uklanjaju plen, ali povratak iz rupe uz preživljen pogodak ga čuva.

## Tehnički ugovor

- `Arsenal.swift`: naprave, oblici efekata, inventar plena i aktivacije.
- `WeaponArt.swift`: slikani atlas osam projektila, rezervni vektori i zasebni
  pokreti zgloba. Naslikani hvat/vrat i proporcije junaka nisu menjani.
- `ShotNode.arsenalPayload`: sidra, latice i izdanci nastaju tek kad projektil
  stigne. Dupli kontakt u susednom frejmu nije novi pogodak; povratna oružja
  imaju najviše dva pogotka po meti i najmanje 0,28 s između njih.
- `GameScene.arsenalStrike`: jedina geometrijska petlja novih pogodaka;
  koristi `dealDamage`/`dealBossDamage`, postojeće odbrane i bodovanje.
- Efekti se obrađuju u simulacionom vremenu, ne preko odloženih damage akcija.
  Pauza, hit-stop i smrt vlasnika zaustavljaju nove pogotke.
- Svi izvorni CharID/SkillDef ID-jevi su sačuvani. Stari Profile slotovi se ne
  prepisuju; runtime koristi HeroArsenal.coreSkills plus prazan slot plena.
  Mech.arsenal koristi osam dotadašnjih početnih trećih veština.
- Maksimum 16 aktivnih naprava po igraču, 3 po ličnom tipu. Oružje nije
  sastavljeno od novih bitmap ruku: anatomija i popravke 7.20.1 ostaju iste.
- `--arsenal-smoke` proverava 8 junaka i 4 plena na 30/60/120 koraka/s.
- Za tihu vidljivu probu svih aktivnih slotova dodaj `VETROMIR_QA_ARSENAL=1`
  uz postojeću performance probu i `VETROMIR_QA_MOVE=1`.

Backup pre promene: `../vetromir-backups/vetromir-pre-weapon-polish-20260912.tar.gz`.
7.25 je macOS izdanje za besplatno preuzimanje na GitHubu; nema novog mobilnog izdanja.
Koristi originalni ImageGen atlas iz 7.22; novi borbeni potezi su kodni efekti.
Nema novih biblioteka ni zvukova; četiri nova neprijateljska atlasa su odvojena od oružja.
