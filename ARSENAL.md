# Arsenal 7.21

Svaki junak ima lično osnovno oružje i zaseban sporedni napad. Početni
sporedni napad je u trećem slotu; igrač može da ga rasporedi u radnji kao
i ranije. Bliska borba, lični potez O/R3 i kupljene veštine ostaju dostupni.

| Junak | Osnovno oružje | Sporedni napad |
| --- | --- | --- |
| Vetromir | Astrolab vetrova: prsten prvo kruži pa odlazi ka nišanu | Džepna oluja: postavljen vrtlog privlači i usporava mete |
| Vukašin | Povratne makaze: dva kraka odlaze i vraćaju se suprotnim lukovima | Zatvaranje makaza: kraci se zatvaraju 0,16 s, pa pogađaju jednom po meti |
| Zorvid | Nebeski šestar: strele ostavljaju najviše tri vazdušna sidra | Prelom sazvežđa: povezuje i troši sidra svetlosnim rezom |
| Gvozdan | Kotao klikera: lobuje najviše tri mine, eksplodiraju blizu mete | Crveno dugme: trenutno detonira postavljene mine |
| Ognjen | Suncobran svitanja: kratak potisak kroz red, odbija jedno đule | Ogledalo podneva: 2,4 s odbrane, najviše četiri odbijena đuleta |
| Rujana | Kalem rumene niti: naizmenično bliža i dalja tačka povezuju se reznom niti | Razboj svile: žičana zamka udara u tri odvojena takta |
| Jasenka | Zvončić semena: najviše tri stražara sami nišane obližnje mete | Rascvetavanje: stražari se troše u ukrštenom rafalu latica |
| Noćena | Fenjer jučerašnjice: povratni srp pamti tri poslednja mesta pogotka | Još jednom juče: odloženi udari na zapamćenim mestima |

Ako nema postavljenih naprava, Zorvid/Rujana/Noćena koriste trenutni nišan,
Gvozdan kratak krug oko sebe, a Jasenka jedan rafal sa štapa. Nema besplatne
teleportacije, beskonačne zaštite niti menjanja fizičkih dimenzija junaka.
Prethodne terenske moći privremeno koriste svoje postojeće obrasce oružja.
Mine sleću na prolazne platforme samo odozgo, a od čvrstog zida se odbijaju.
Nit Rujane ostaje vezana za život zamke i ne nestaje dok je igra pauzirana.

## Plen

Treći poraženi običan neprijatelj daje prvi osvojivi napad. Zatim svaki sedmi
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
zamena predmeta ga ne preskače. Poslednje punjenje vraća prethodno opremljenu
veštinu; držano dugme se mora otpustiti pre njene upotrebe. Smrt i završetak
nivoa uklanjaju plen, ali povratak iz rupe uz preživljen pogodak ga čuva.

## Tehnički ugovor

- `Arsenal.swift`: naprave, oblici efekata, inventar plena i aktivacije.
- `GameScene.arsenalStrike`: jedina geometrijska petlja novih pogodaka;
  koristi `dealDamage`/`dealBossDamage`, postojeće odbrane i bodovanje.
- Efekti se obrađuju u simulacionom vremenu, ne preko odloženih damage akcija.
  Pauza, hit-stop i smrt vlasnika zaustavljaju nove pogotke.
- Svi izvorni CharID/SkillDef ID-jevi su sačuvani. Profil nije migriran niti
  je korisniku prepisan raspored slotova. Novi Mech.arsenal koristi osam
  dotadašnjih početnih trećih veština.
- Maksimum 16 aktivnih naprava po igraču, 3 po ličnom tipu. Oružje nije
  sastavljeno od novih bitmap ruku: anatomija i popravke 7.20.1 ostaju iste.
- `--arsenal-smoke` proverava 8 junaka i 4 plena na 30/60/120 koraka/s.
- Za tihu vidljivu probu svih aktivnih slotova dodaj `VETROMIR_QA_ARSENAL=1`
  uz postojeću performance probu i `VETROMIR_QA_MOVE=1`.

Backup pre promene: `../vetromir-backups/vetromir-pre-arsenal-7.21-20260909.tar.gz`.
Izdanje 7.21 namenjeno je javnom macOS preuzimanju. Bez novih audio/PNG
resursa i bez novog mobilnog builda. Sirovi muzički izvori se ne objavljuju.
