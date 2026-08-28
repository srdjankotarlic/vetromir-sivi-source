# Instalacija na Mac

## Zahtevi

- Apple Silicon Mac (M1 ili noviji)
- macOS 13 Ventura ili noviji
- oko 100 MB slobodnog prostora za aplikaciju i profil

## Preporučena instalacija

1. Na stranici **Releases** preuzmi fajl koji se završava sa
   `macOS-Apple-Silicon.dmg`. Nemoj preuzimati automatski GitHub arhivirani izvorni kod
   ako samo želiš da igraš.
2. Po želji proveri paket komandom `shasum -a 256 ime-fajla.dmg` i uporedi rezultat sa
   `SHA256SUMS.txt` iz istog izdanja.
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

## Pokretanje iz izvornog koda

Na Macu sa instaliranim Swift 5.9 ili novijim:

```bash
swift build
./.build/debug/Vetromir --smoke
./build-app.sh
```

Gotova lokalna aplikacija biće napravljena na `~/Desktop/Vetromir.app`.
