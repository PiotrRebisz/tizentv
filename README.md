# tizentv

Moja wersja **TizenTube** (YouTube bez reklam na telewizorze) z dodatkami: przyciski Wyłącz ekran, Dźwięk i Jakość na pasku odtwarzacza, odtwarzanie po przewinięciu, pauza jednym kliknięciem OK oraz głośność i przewijanie, które nie włączają wyłączonego ekranu.

## Instrukcje instalacji

- 📺 **Samsung (Tizen)**: [INSTRUKCJA-Samsung.md](INSTRUKCJA-Samsung.md)
- 🤖 **Google TV / Android TV**: [INSTRUKCJA-GoogleTV.md](INSTRUKCJA-GoogleTV.md)

## Pliki do pobrania

- Samsung: https://github.com/PiotrRebisz/tizentv/releases/tag/Samsung
- Google TV / Android TV: https://github.com/PiotrRebisz/tizentv/releases/tag/Android

| Plik | Dla |
| --- | --- |
| `TizenTube.wgt` | Samsung: aplikacja TizenTube |
| `TizenTube-Start.wgt` | Samsung: program uruchamiający (tego używać na co dzień) |
| `TizenTube-Android-32bit.apk` | Google TV / Android TV |
| `userScript.js` (w repozytorium) | skrypt pobierany automatycznie przez wersję na Google TV |

### Dla właściciela: nowa wersja plików

Wydania mają stałe tagi `Samsung` i `Android`, dzięki czemu linki w instrukcjach się nie zmieniają. Przy nowej wersji edytuj wydanie (**Edit**), usuń stary plik i dodaj nowy **o tej samej nazwie**.

## Licencja i kod źródłowy

To zmodyfikowana wersja [TizenTube](https://github.com/reisxd/TizenTube) (autor: reisxd), udostępniana na licencji **GNU GPL v3.0** (pełny tekst: [LICENSE](LICENSE)).

Kod źródłowy moich zmian: [zrodla/tizentube-zmiany.diff](zrodla/tizentube-zmiany.diff). To diff katalogu `mods/` względem reisxd/TizenTube, commit `f99945a84ff767bf14ad8c1146e8e3fd49a3d628` (skrypt `@foxreis/tizentube` 1.15.2).

Jak zbudować `userScript.js` samodzielnie (potrzebne git i Node.js):

```
git clone https://github.com/reisxd/TizenTube
cd TizenTube
git checkout f99945a84ff767bf14ad8c1146e8e3fd49a3d628
git apply ../tizentube-zmiany.diff
cd mods
npm ci
npm run build
```

Wynik trafia do `dist/userScript.js` i jest identyczny z plikiem `userScript.js` w tym repozytorium.

Oparte na [TizenTube](https://github.com/reisxd/TizenTube) i [TizenTube Cobalt](https://github.com/reisxd/TizenTubeCobalt) autorstwa reisxd.
