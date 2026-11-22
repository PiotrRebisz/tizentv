# TizenTube na telewizorze Samsung (Tizen): instrukcja instalacji

YouTube bez reklam na telewizorze Samsung, w mojej wersji z dodatkami:

- przyciski na pasku odtwarzacza: **Wyłącz ekran**, **Dźwięk**, **Jakość**,
- **Odtwarzaj po przewinięciu**: po przewinięciu film sam rusza dalej,
- **Pauza jednym kliknięciem OK**: gdy pasek jest schowany, jedno OK zatrzymuje film,
- **Głośność i przewijanie nie włączają ekranu**, gdy ekran jest wyłączony,
- pełne spolszczenie i powiadomienie o nowych wersjach.

Instrukcja jest sprawdzona na **Samsung QE55Q67DAUXXH (2024, Tizen 8)**. Powinna działać na telewizorach Samsung z Tizen 6 (rok 2021) i nowszych.

Instalacja odbywa się **z telefonu z Androidem**, bez komputera.

---

## Czego potrzebujesz

| Co | Skąd |
| --- | --- |
| Telewizor Samsung z Tizen 6 lub nowszym (2021+) | |
| Telefon z Androidem w **tej samej sieci Wi-Fi** co telewizor | |
| Darmowe konto Samsung (do podpisania aplikacji, wymagane od Tizen 7) | https://account.samsung.com |
| Aplikacja **Apps2Samsung** na telefon | https://github.com/Apps2Samsung/Apps2Samsung/releases |
| Paczka **TizenTube.wgt** | https://github.com/PiotrRebisz/tizentv/releases/download/Samsung/TizenTube.wgt |
| Paczka **TizenTube-Start.wgt** | https://github.com/PiotrRebisz/tizentv/releases/download/Samsung/TizenTube-Start.wgt |

Oba pliki są też na stronie wydania: https://github.com/PiotrRebisz/tizentv/releases/tag/Samsung

> **Dlaczego dwie paczki?** **TizenTube** to sama aplikacja. **TizenTube Start** to program uruchamiający: najpierw włącza usługę TizenTube w tle, a potem otwiera aplikację. Na tym telewizorze TizenTube uruchamiany bezpośrednio często pokazuje błąd sieci, dlatego na co dzień otwiera się **TizenTube Start**.

---

## Krok 1. Przygotuj telefon

Na telefonie **nie trzeba włączać opcji programisty**. Wystarczy pozwolić przeglądarce instalować aplikacje spoza Sklepu Play.

1. Na telefonie otwórz stronę wydań Apps2Samsung: https://github.com/Apps2Samsung/Apps2Samsung/releases
2. W najnowszym wydaniu (oznaczonym jako *Latest*) rozwiń **Assets** i pobierz plik kończący się na **`-android.apk`**.
3. Otwórz pobrany plik. Jeśli telefon zapyta, zezwól przeglądarce na instalowanie aplikacji z nieznanych źródeł:
   **Ustawienia → Aplikacje → (przeglądarka, np. Chrome) → Instaluj nieznane aplikacje → Zezwalaj**.
4. Zainstaluj Apps2Samsung.

Zamiast pliku APK można użyć **Obtainium** (wtedy Apps2Samsung sam się aktualizuje): w Obtainium dodaj aplikację z adresu `https://github.com/Apps2Samsung/Apps2Samsung`.

### Sprawdź adres IP telefonu

Będzie potrzebny w kroku 2.

**Ustawienia → Wi-Fi (lub Połączenia → Wi-Fi) → kliknij swoją sieć (ikona zębatki) → Adres IP**, np. `192.168.1.10`.

> Wskazówka: w routerze można przypisać telefonowi stały adres IP (rezerwacja DHCP). Wtedy nie trzeba zmieniać ustawień telewizora przy każdej instalacji.

---

## Krok 2. Włącz tryb programisty na telewizorze

1. Na pilocie naciśnij **Home** i przejdź do **Aplikacje**.
2. Będąc w **Aplikacjach**, wpisz na pilocie **`12345`**. Jeśli pilot nie ma cyfr, użyj przycisku **123** i wpisz cyfry na ekranie.
3. Pojawi się okno **Developer mode**:
   - przestaw **Developer mode** na **On**,
   - w polu **Host PC IP** wpisz **adres IP telefonu** z kroku 1 (normalnie, np. `192.168.1.10`),
   - zatwierdź **OK**.
4. **Uruchom telewizor ponownie**: przytrzymaj przycisk zasilania na pilocie, aż zobaczysz logo Samsunga.

Jeśli później Apps2Samsung nie może połączyć się z telewizorem, odłącz telewizor z prądu na 10 do 15 sekund i włącz ponownie.

Sprawdź też adres IP telewizora: **Ustawienia → Ogólne (lub Połączenie) → Sieć → Stan sieci → Ustawienia IP**.

---

## Krok 3. Pobierz paczki TizenTube na telefon

Na telefonie pobierz oba pliki:

- **TizenTube.wgt**: https://github.com/PiotrRebisz/tizentv/releases/download/Samsung/TizenTube.wgt
- **TizenTube-Start.wgt**: https://github.com/PiotrRebisz/tizentv/releases/download/Samsung/TizenTube-Start.wgt

Trafią do folderu **Pobrane**.

---

## Krok 4. Ustaw Apps2Samsung (jednorazowo)

1. Otwórz **Apps2Samsung** na telefonie.
2. Wejdź w **ustawienia** (ikona zębatki) i przewiń do sekcji **Certificate**:
   - typ certyfikatu: **Partner**,
   - włącz **Force Samsung Certificate**.
3. Gdy aplikacja poprosi o logowanie, zaloguj się **kontem Samsung**. Apps2Samsung sam utworzy certyfikat dla Twojego telewizora i będzie go używał przy kolejnych instalacjach.

> Bez certyfikatu **Partner** i **Force Samsung Certificate** TizenTube zainstaluje się, ale po uruchomieniu pokaże komunikat **„A network error has occurred”**.

---

## Krok 5. Zainstaluj obie paczki

> Jeśli masz już zainstalowane **oficjalne** TizenTube albo wersję zainstalowaną innym programem, najpierw je usuń: na telewizorze zaznacz aplikację, przytrzymaj OK i wybierz **Usuń**. Inaczej instalacja skończy się błędem *„Author certificate not match”*.

1. W Apps2Samsung wybierz swój telewizor z listy. Jeśli go nie ma, wpisz ręcznie adres IP telewizora.
2. W liście **Release** przewiń na sam dół i wybierz **Custom WGT File**.
3. Wskaż plik **TizenTube.wgt** z folderu Pobrane.
4. Naciśnij **Install** i poczekaj na komunikat o udanej instalacji.
5. Powtórz punkty 2 do 4 dla pliku **TizenTube-Start.wgt**.

---

## Krok 6. Pierwsze uruchomienie

1. Na telewizorze otwórz **Aplikacje** i uruchom **TizenTube Start**.
2. Zobaczysz napis *„Uruchamianie TizenTube…”*. Po chwili otworzy się TizenTube.
3. Zaloguj się do YouTube tak samo jak w zwykłej aplikacji.
4. Przenieś **TizenTube Start** na ekran główny: zaznacz go, przytrzymaj OK i wybierz **Dodaj do ekranu głównego** (lub **Przenieś**).

Na co dzień uruchamiaj **TizenTube Start**, nie samo TizenTube.

### Ustawienia moich dodatków

W TizenTube otwórz ustawienia (ikona TizenTube w menu bocznym). W sekcji odtwarzacza znajdziesz przełączniki:

- **Pokaż przycisk wyłączania ekranu**, **Pokaż przycisk dźwięku**, **Pokaż przycisk jakości**,
- **Odtwarzaj po przewinięciu**,
- **Pauza jednym kliknięciem OK**,
- **Głośność i przewijanie nie włączają ekranu**.

Wszystkie są domyślnie włączone.

---

## Aktualizacja

Moja wersja **nie aktualizuje się sama**, bo skrypt jest wbudowany w paczkę. Gdy pojawi się nowa wersja:

1. Pobierz na telefon nowe pliki **TizenTube.wgt** i **TizenTube-Start.wgt** (te same linki co w kroku 3).
2. Jeśli adres IP telefonu się zmienił, popraw **Host PC IP** w trybie programisty (krok 2) i uruchom telewizor ponownie.
3. Zainstaluj obie paczki przez Apps2Samsung tak jak w kroku 5. **Nie trzeba** usuwać starej wersji: nowsza instaluje się na starszą i ustawienia zostają.

W ustawieniach TizenTube, w sekcji **Aktualizacje TizenTube**, można sprawdzić, czy autor TizenTube wydał nowszą wersję.

---

## Rozwiązywanie problemów

| Problem | Co zrobić |
| --- | --- |
| Apps2Samsung nie widzi telewizora | Telefon i telewizor muszą być w tej samej sieci. Wpisz IP telewizora ręcznie. Sprawdź, czy **Host PC IP** to aktualny adres telefonu. Odłącz telewizor z prądu na 10 do 15 s. |
| *„Author certificate not match”* | Na telewizorze jest wersja z innym podpisem. Usuń TizenTube (i TizenTube Start) z telewizora i zainstaluj ponownie. |
| *„A network error has occurred”* po uruchomieniu | Uruchamiaj przez **TizenTube Start**. Sprawdź, czy przy instalacji był certyfikat **Partner** i **Force Samsung Certificate**. Po włączeniu telewizora z prądu poczekaj kilka sekund i spróbuj ponownie. |
| Po wyłączeniu trybu programisty aplikacje zniknęły | Tryb programisty musi zostać włączony. Włącz go ponownie i zainstaluj paczki jeszcze raz. |
| Logowanie Samsung kończy się błędem 403 | Odczekaj 15 do 30 minut i spróbuj ponownie, bez wielokrotnego ponawiania. |

---

## Źródła

- TizenTube (autor: reisxd): https://github.com/reisxd/TizenTube
- Oficjalna instrukcja instalacji TizenTube: https://github.com/reisxd/TizenTube/blob/main/docs/README.md
- Apps2Samsung: https://github.com/Apps2Samsung/Apps2Samsung
- FAQ Apps2Samsung (tryb programisty, błędy): https://github.com/Apps2Samsung/Apps2Samsung/wiki/FAQ
