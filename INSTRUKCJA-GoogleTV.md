# TizenTube na Google TV / Android TV: instrukcja instalacji

YouTube bez reklam na Google TV, w mojej wersji z dodatkami:

- przyciski na pasku odtwarzacza: **Wyłącz ekran**, **Dźwięk**, **Jakość**,
- **Odtwarzaj po przewinięciu**: po przewinięciu film sam rusza dalej,
- **Pauza jednym kliknięciem OK**: gdy pasek jest schowany, jedno OK zatrzymuje film,
- **Głośność i przewijanie nie włączają ekranu**, gdy ekran jest wyłączony,
- pełne spolszczenie.

Instrukcja jest sprawdzona na **Google TV Streamer**. Powinna działać też na innych urządzeniach z Google TV / Android TV (np. Chromecast z Google TV).

Aplikację instaluje się bezpośrednio na telewizorze przez aplikację **Downloader**. Telefon jest potrzebny tylko do opcjonalnych poleceń ADB (krok 6).

---

## Czego potrzebujesz

| Co | Skąd |
| --- | --- |
| Google TV Streamer (lub inne urządzenie z Google TV) | |
| Aplikacja **Downloader by AFTVnews** na telewizorze | Sklep Google Play na telewizorze |
| Plik **TizenTube-Android-32bit.apk** (moja wersja) | https://github.com/PiotrRebisz/tizentv/releases/download/android/TizenTube-Android-32bit.apk |
| (opcjonalnie) Aplikacja **Remote ADB Shell** na telefon | Sklep Google Play na telefonie |

Plik jest też na stronie wydania: https://github.com/PiotrRebisz/tizentv/releases/tag/android

> **Ważne:** Google TV Streamer potrzebuje wersji **32-bit**. Wersja 64-bit (`arm64`) kończy się komunikatem *„Aplikacja jest niezgodna z Twoim telewizorem”*.

---

## Krok 1. Włącz opcje programisty na Google TV

1. Otwórz **Ustawienia** (ikona zębatki w prawym górnym rogu ekranu głównego).
2. Wejdź w **System → Informacje**.
3. Przewiń do pozycji **Kompilacja systemu Android TV OS** i naciśnij na niej OK **7 razy**, aż pojawi się komunikat *„Jesteś teraz programistą”*.
4. W **Ustawienia → System** pojawi się nowa pozycja **Opcje programisty**.

Opcje programisty są potrzebne, żeby telewizor pozwolił instalować aplikacje spoza Sklepu Play.

---

## Krok 2. Zainstaluj Downloader

1. Na telewizorze otwórz **Sklep Google Play**.
2. Wyszukaj **Downloader** (jeśli nie wyskakuje, wpisz **aftvnews**).
3. Zainstaluj **Downloader by AFTVnews**.

### Zezwól Downloaderowi na instalowanie aplikacji

**Ustawienia → Aplikacje → Zabezpieczenia i ograniczenia → Nieznane źródła → Downloader → Dozwolone**.

Możesz też pominąć ten punkt. Wtedy przy pierwszej instalacji z Downloadera telewizor sam pokaże komunikat z przyciskiem **Ustawienia**, w którym włączysz Downloader.

---

## Krok 3. Usuń oficjalne TizenTube Cobalt (jeśli było zainstalowane)

Moja wersja jest podpisana moim kluczem, więc **nie zainstaluje się na wersję oficjalną**. Jeśli masz oficjalne TizenTube Cobalt:

**Ustawienia → Aplikacje → TizenTube → Odinstaluj**.

Kolejne aktualizacje mojej wersji instalują się już bez odinstalowywania.

---

## Krok 4. Pobierz i zainstaluj TizenTube

1. Otwórz **Downloader**. Przy pierwszym uruchomieniu zezwól na dostęp do plików.
2. W polu adresu wpisz:

   ```
   https://github.com/PiotrRebisz/tizentv/releases/download/android/TizenTube-Android-32bit.apk
   ```

   i wybierz **Go**.
3. Poczekaj na pobranie pliku (około 80 MB).
4. Wybierz **Zainstaluj**. Jeśli telewizor zapyta o zgodę dla Downloadera, wybierz **Ustawienia**, włącz Downloader i wróć.
5. Po instalacji Downloader zaproponuje usunięcie pliku APK: wybierz **Usuń**, żeby nie zajmował miejsca.

> Wskazówka: długi adres łatwiej wpisać, jeśli zrobisz z niego krótki link (np. w serwisie is.gd) i wpiszesz w Downloaderze krótki adres.

---

## Krok 5. Pierwsze uruchomienie

1. Uruchom **TizenTube** z listy aplikacji.
2. Zaloguj się do YouTube tak samo jak w zwykłej aplikacji.
3. Możesz dodać TizenTube do ulubionych na ekranie głównym.

Aplikacja przy każdym uruchomieniu pobiera mój skrypt z GitHuba:
`https://cdn.jsdelivr.net/gh/PiotrRebisz/tizentv@main/userScript.js`

Dzięki temu **nowe funkcje trafiają na telewizor bez reinstalacji APK** (patrz „Aktualizacja”).

### Ustawienia moich dodatków

W TizenTube otwórz ustawienia (ikona TizenTube w menu bocznym). W sekcji odtwarzacza znajdziesz przełączniki:

- **Pokaż przycisk wyłączania ekranu**, **Pokaż przycisk dźwięku**, **Pokaż przycisk jakości**,
- **Odtwarzaj po przewinięciu**,
- **Pauza jednym kliknięciem OK**,
- **Głośność i przewijanie nie włączają ekranu**.

Wszystkie są domyślnie włączone.

---

## Krok 6 (opcjonalnie). Polecenia ADB z telefonu: Remote ADB Shell

Przydaje się do zmian, których nie ma w menu Google TV, np. czasu wygaszacza ekranu. Na telefonie **nie trzeba włączać opcji programisty**.

### Na telewizorze

1. **Ustawienia → System → Opcje programisty**.
2. Włącz **Debugowanie USB**. Jeśli jest pozycja **Debugowanie bezprzewodowe**, włącz ją też.
3. Sprawdź adres IP telewizora: **Ustawienia → Sieć i internet → (Twoja sieć)**, np. `192.168.86.102`.

### Na telefonie

1. Zainstaluj **Remote ADB Shell** ze Sklepu Google Play: https://play.google.com/store/search?q=Remote%20ADB%20Shell&c=apps
2. Dodaj urządzenie: adres IP telewizora i port **5555** (np. `192.168.86.102:5555`).
3. Na telewizorze pojawi się pytanie o zezwolenie na debugowanie: zaznacz **Zawsze zezwalaj z tego komputera** i wybierz **OK**.
4. Otwórz terminal (**Launch ADB Terminal Console**) i wpisuj polecenia **bez** przedrostka `adb shell`.

### Przydatne polecenia

| Co | Polecenie |
| --- | --- |
| Wygaszacz ekranu po 2 minutach | `settings put system screen_off_timeout 120000` |
| Sprawdzenie czasu wygaszacza | `settings get system screen_off_timeout` |
| Lista zainstalowanych aplikacji | `pm list packages -3` |

Czas wygaszacza podaje się w milisekundach (60000 = 1 minuta). Zmiana czasu w zwykłych ustawieniach Google TV nadpisze tę wartość.

> Bezpieczeństwo: gdy nie używasz poleceń ADB, możesz wyłączyć **Debugowanie USB**. Włączone debugowanie pozwala urządzeniom w sieci łączyć się z telewizorem (każde nowe połączenie trzeba jednak zatwierdzić na ekranie).

---

## Aktualizacja

- **Nowe funkcje skryptu** (najczęstszy przypadek): po wgraniu nowego `userScript.js` do repozytorium i odświeżeniu pamięci podręcznej jsDelivr wystarczy na telewizorze **Ustawienia → Aplikacje → TizenTube → Wymuś zatrzymanie** i uruchomić TizenTube ponownie.
- **Nowa wersja APK** (rzadko): zainstaluj nowy plik tak jak w kroku 4. Instaluje się na starą wersję, ustawienia zostają.

### Dla właściciela repozytorium: publikacja nowego skryptu

1. Podmień `userScript.js` w repozytorium (gałąź `main`).
2. Otwórz link odświeżający jsDelivr: https://purge.jsdelivr.net/gh/PiotrRebisz/tizentv@main/userScript.js
   W odpowiedzi powinno być `"status": "finished"`. Jeśli ścieżka jest oznaczona jako `throttled`, odczekaj około pół godziny i otwórz link ponownie.
3. Bez odświeżenia jsDelivr może przez kilka godzin podawać starą wersję skryptu.

---

## Rozwiązywanie problemów

| Problem | Co zrobić |
| --- | --- |
| *„Aplikacja jest niezgodna z Twoim telewizorem”* | Pobrano wersję 64-bit. Użyj pliku **TizenTube-Android-32bit.apk**. |
| *„Aplikacja nie została zainstalowana”* | Na telewizorze jest wersja z innym podpisem (np. oficjalna). Odinstaluj ją (krok 3) i zainstaluj ponownie. |
| Brak przycisku instalacji w Downloaderze | Zezwól Downloaderowi na instalowanie aplikacji (krok 2). Jeśli nie ma tej opcji, włącz najpierw opcje programisty (krok 1). |
| Nowa funkcja nie działa po aktualizacji skryptu | Odśwież jsDelivr (link wyżej), potem **Wymuś zatrzymanie** TizenTube i uruchom ponownie. |
| Remote ADB Shell się nie łączy | Sprawdź IP telewizora, port 5555 i czy **Debugowanie USB** jest włączone. Telefon i telewizor muszą być w tej samej sieci. |

---

## Źródła

- TizenTube Cobalt (autor: reisxd): https://github.com/reisxd/TizenTubeCobalt
- Instalacja przez Downloader na Google TV Streamer (AFTVnews): https://www.aftvnews.com/?p=43668
- Moja wersja: https://github.com/PiotrRebisz/tizentv
