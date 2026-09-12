# Instalacija na Mac

## Zahtevi

- Apple Silicon Mac (M1 ili noviji)
- macOS 13 Ventura ili noviji
- najmanje 200 MB slobodnog prostora za aplikaciju i profil

## Preporučena instalacija

1. Na stranici **Releases** preuzmi fajl koji se završava sa
   `macOS-Apple-Silicon-Serbian-English.dmg`. Nemoj preuzimati automatski GitHub arhivirani izvorni kod
   ako samo želiš da igraš.
2. Po želji proveri paket komandom `shasum -a 256 ime-fajla.dmg` i uporedi rezultat sa
   `SHA256SUMS-v7.25.txt` iz istog izdanja.
3. Otvori DMG i prevuci `Vetromir.app` na prečicu `Applications`.
4. Pokreni igru iz foldera Applications.

## Prvo pokretanje bez notarizacije

Ovo izdanje je provereno i potpisano, ali nije poslato Apple notarizacionoj službi.
Zato Gatekeeper može da prikaže upozorenje. Ako si paket preuzeo sa zvanične stranice
projekta i checksum se poklapa, prvo pokušaj da otvoriš aplikaciju, zatim idi na
**System Settings > Privacy & Security** i izaberi **Open Anyway**. Nemoj isključivati
Gatekeeper niti koristiti terminalske komande koje uklanjaju zaštitu celog sistema.

## Čuvanje napretka

Profil i rang-lista nalaze se u
`~/Library/Application Support/Vetromir/profile.json`. Brisanje same aplikacije ne
briše ovaj fajl.

## Koji GitHub fajl da izaberem

Preuzmi DMG ili ZIP aplikacije uz izdanje 7.25. Automatski GitHub paket
"Source code" sadrži dokumentaciju distributivnog repozitorijuma, ne igru.
Za igranje ti nisu potrebni Xcode ni razvojni alati.
