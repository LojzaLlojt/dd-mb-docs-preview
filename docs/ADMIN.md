# DD-MB – Admin Panel

---

- [English (EN)](#english)
- [Čeština (CZ)](#čeština)
- [Slovenčina (SK)](#slovenčina)
- [Polski (PL)](#polski)
- [Deutsch (DE)](#deutsch)
- [Magyar (HU)](#magyar)

---

## English

### Overview

The Admin Panel is the central control interface for DD-MB. It is accessible from the login screen by selecting the **Admin** tab.

The panel is organised into the following sections:

| Section | Purpose |
|---|---|
| **Import ZIP** | Upload the layout ZIP file |
| **Sound Library** | Upload and manage alert sounds |
| **Graphical Timetables** | Upload SVG timetable files (optional) |
| **State Operation** | Reset or delete the current layout |
| **Session Time** | Mark trains as done up to a target time |
| **Model Time** | Internal clock control |
| **Time Synchronisation** | Broadcast or receive model time (Client/Server) |
| **Circulations** | Import working timetable (Rosters, optional) |
| **Export / Import Configuration** | Backup and restore station settings |
| **Station Configuration** | Per-station setup for dispatchers |
| **Passwords** | Passwords for Admin portal, Rosters and individual stations |

> [!IMPORTANT]
> Steps relevant to event preparation are described in [INITIAL_SETUP.md](./INITIAL_SETUP.md).

---

### Import ZIP

Upload a `.zip` file that contains the layout definition. This replaces the currently active layout. See [INITIAL_SETUP.md](./INITIAL_SETUP.md) for creating layout file.

> [!WARNING]
> Importing a new ZIP resets all train states and dispatcher sessions.

---

### Sound Library

Upload custom alert sounds (any common audio format). The library lists all uploaded files.

- **Default alert** – select which sound is played when a dispatcher receives a new incoming offer.
- Each sound can be previewed (▶) and deleted.
- The built-in default sound cannot be deleted.

---

### Graphical Timetables

Upload one or more SVG timetable files. Uploaded timetables become available in the dispatcher view (timetable button in the header). Each file can be previewed in the browser or deleted.

---

### State Operation

Two buttons control the overall lifecycle of a session:

#### Reset Layout

Resets all train states back to the beginning of the day (time 00:00). All **completed** circulations are made active again. Use this when the operational day has finished and you want to start a new round with the same layout.

> Does **not** delete station configuration or passwords.

#### Delete Layout

Completely removes the layout from DD-MB — all stations, train states and route blocks are wiped. Use this when preparing for a new event with a different layout.

---

### Session Time

Allows you to advance the session to a specific model time (format `HH:MM`). Trains whose scheduled time ends before the target are automatically marked as **done**. Trains that have not yet started are added to their circulation.

This is useful at the beginning of an event to skip past midnight trains that would otherwise already be finished.

---

### Model Time

Controls the DD-MB internal clock — used when DD-MB is not synchronised to an external time source.

- **Initial time** – the starting time when the layout is loaded or reset.
- **Speed** – playback speed from 0.5× to 4× in 0.5× steps.
- Changes take effect immediately and are reflected in all dispatcher views.

---

### Time Synchronisation

Determines how DD-MB interacts with model-time sources on the network.

| Mode | Behaviour |
|---|---|
| **Off** | DD-MB uses its own internal clock only |
| **Client** | DD-MB listens to an external time broadcast and synchronises its clock to it |
| **Server** | DD-MB broadcasts its own clock to the network (e.g. for standalone display clocks) |

When using **Client** or **Server** mode, configure the protocol, multicast address and UDP port to match the other devices on the network.

---

### Circulations (optional)

Import a `circulations.svg` file exported from a working timetable tool. This populates the **Rosters** portal with driver-circulation assignments.

- Once imported, the total number of imported circulations is displayed.
- Circulations can be deleted if the Rosters feature is not used.

See [ROSTERS.md](./ROSTERS.md) for details on the Rosters workflow.

---

### Export / Import Configuration

Backs up and restores all station configuration (neighbour assignments, block slots, hidden/simplified flags, passwords, timetable assignments, etc.) as a single JSON file.

- **Export all** – downloads the configuration of every station as `station-config.json`.
- **Import** – uploads a previously exported JSON and applies it immediately.

> Use this to transfer a prepared configuration to a different server or to restore it after a layout re-import.

---

### Station Configuration

Displays all stations in the current layout. Expand a station to configure it:

| Setting | Description |
|---|---|
| **Left / Right neighbours** | Which neighbouring stations appear in the left or right block panel of the dispatcher view |
| **Block slots** | Number of parallel tracks available between this station and a neighbour |
| **Hidden** | Station is operated automatically (no dispatcher login needed) |
| **Simplified** | Station uses the simplified Driver View instead of the full dispatcher view |
| **Timetable** | Which graphical timetable file is shown in this station's dispatcher view |
| **Phone number** | Optional phone number displayed in the dispatcher header |
| **Alert sound** | Override the default alert sound for this station |
| **Password** | Set a custom login password for this station's dispatcher |

---

### Passwords

Set passwords to secure access to the different parts of DD-MB:

- **Admin password** – protects the Admin Panel. If left empty, the default from the server environment (`ADMIN_PASSWORD`) is used.
- **Rosters password** – protects the Rosters portal. If left empty, the default from the server environment (`ROSTER_PASSWORD`) is used.
- **Station passwords** – set per station in **Station Configuration** above.

> Passwords are stored in the server state file and survive restarts.

---

---

## Čeština

### Přehled

Admin Panel je centrální ovládací rozhraní DD-MB. Dostupný z přihlašovací obrazovky záložkou **Admin**.

Panel je rozdělen do následujících sekcí:

| Sekce | Účel |
|---|---|
| **Import ZIP** | Nahrání ZIP souboru s layoutem |
| **Knihovna zvuků** | Nahrání a správa upozornění |
| **Grafické jízdní řády** | Nahrání SVG souborů jízdních řádů (volitelné) |
| **Správa stavu** | Resetování nebo smazání layoutu |
| **Čas relace** | Označení vlaků jako dokončených do cílového času |
| **Modelový čas** | Ovládání interních hodin |
| **Synchronizace času** | Příjem nebo vysílání modelového času (Client/Server) |
| **Oběhy** | Import pracovního řádu pro Turnusy (volitelné) |
| **Export / import konfigurace** | Záloha a obnovení nastavení stanic |
| **Konfigurace stanic** | Nastavení jednotlivých stanic pro výpravčí |
| **Hesla** | Hesla pro Admin portal, Turnusy a jednotlivé stanice |

> [!IMPORTANT]
> Kroky relevantní pro přípravu akce jsou popsány v [INITIAL_SETUP.md](./INITIAL_SETUP.md).

---

### Import ZIP

Nahrajte `.zip` soubor s definicí layoutu. Nahradí aktuálně aktivní layout. Postup vytvoření souboru s layoutem najdete v [INITIAL_SETUP.md](./INITIAL_SETUP.md).

> [!WARNING]
> Import nového ZIP resetuje všechny stavy vlaků a relace výpravčích.

---

### Knihovna zvuků

Nahrávejte vlastní zvuky upozornění (běžné audio formáty). Knihovna zobrazuje všechny nahrané soubory.

- **Výchozí upozornění** – vyberte zvuk přehrávaný při příchozí nabídce vlaku.
- Každý zvuk lze přehrát (▶) a smazat.
- Výchozí systémový zvuk nelze smazat.

---

### Grafické jízdní řády

Nahrajte jeden nebo více SVG souborů s jízdními řády. Nahrané jízdní řády budou dostupné v pohledu výpravčího (tlačítko v záhlaví). Každý soubor lze zobrazit nebo smazat.

---

### Správa stavu

Dvě tlačítka ovládají životní cyklus relace:

#### Reset layoutu

Resetuje všechny stavy vlaků na začátek dne (čas 00:00). Všechny **dokončené** oběhy se znovu aktivují. Použijte po skončení provozního dne pro nový provoz se stejným layoutem.

> **Nemaže** konfiguraci stanic ani hesla.

#### Smazat layout

Kompletně odstraní layout z DD-MB – všechny stanice, stavy vlaků i blokové tabulky. Použijte při přípravě nové akce s jiným layoutem.

---

### Čas relace

Umožňuje přejít na konkrétní modelový čas (formát `HH:MM`). Vlaky, jejichž čas odjezdu uplynul před cílovým časem, jsou automaticky označeny jako **dokončené**. Vlaky, které ještě nezačaly, jsou přidány do oběhu.

---

### Modelový čas

Ovládá interní hodiny DD-MB, pokud není synchronizace s externím zdrojem.

- **Počáteční čas** – čas při načtení nebo resetu layoutu.
- **Rychlost** – přehrávací rychlost od 0,5× do 4× s krokem 0,5×.

---

### Synchronizace času

| Režim | Chování |
|---|---|
| **Vypnuto** | DD-MB používá pouze vlastní interní hodiny |
| **Client** | DD-MB naslouchá externímu vysílání a synchronizuje se |
| **Server** | DD-MB vysílá vlastní čas do sítě (např. pro nástupní hodiny) |

---

### Turnusy (volitelné)

Importujte soubor `circulations.svg` exportovaný z nástroje Grafikon. Naplní portál **Turnusy** k přiřazení strojvedoucích k oběhům.

Viz [ROSTERS.md](./ROSTERS.md) pro podrobnosti o práci s Turnusy.

---

### Export / import konfigurace

Záloha a obnovení konfigurace všech stanic jako JSON soubor.

- **Export všech** – stáhne konfiguraci každé stanice jako `station-config.json`.
- **Import** – nahraje dříve exportovaný JSON a aplikuje ho okamžitě.

---

### Konfigurace stanic

Zobrazuje všechny stanice aktuálního layoutu. Rozbalením stanice ji lze konfigurovat:

| Nastavení | Popis |
|---|---|
| **Leví / praví sousedé** | Které sousední stanice se zobrazí v levém/pravém blokovém panelu výpravčího |
| **Sloty bloků** | Počet paralelních kolejí mezi touto stanicí a sousedem |
| **Skrytá** | Stanice je obsluhována automaticky (bez přihlášení výpravčího) |
| **Zjednodušená** | Stanice používá zjednodušený pohled strojvedoucího |
| **Jízdní řád** | Grafický jízdní řád zobrazený u této stanice |
| **Telefonní číslo** | Volitelné telefonní číslo v záhlaví výpravčího |
| **Zvuk upozornění** | Přepis výchozího zvuku pro tuto stanici |
| **Heslo** | Vlastní přihlašovací heslo pro výpravčího této stanice |

---

### Hesla

- **Heslo admina** – chrání Admin Panel. Pokud nevyplněno, použije se výchozí z prostředí serveru.
- **Heslo Turnusů** – chrání portál Turnusy. Pokud nevyplněno, použije se výchozí z prostředí serveru.
- **Hesla stanic** – nastavena v **Konfiguraci stanic** výše.

---

---

## Slovenčina

### Prehľad

Admin Panel je centrálne ovládacie rozhranie DD-MB. Dostupný z prihlasovacej obrazovky záložkou **Admin**.

Panel je rozdelený do nasledujúcich sekcií:

| Sekcia | Účel |
|---|---|
| **Import ZIP** | Nahranie ZIP súboru s layoutom |
| **Knižnica zvukov** | Nahranie a správa upozornení |
| **Grafické cestovné poriadky** | Nahranie SVG súborov cestovných poriadkov (voliteľné) |
| **Správa stavu** | Resetovanie alebo zmazanie layoutu |
| **Čas relácie** | Označenie vlakov ako dokončených do cieľového času |
| **Modelový čas** | Ovládanie interných hodín |
| **Synchronizácia času** | Príjem alebo vysielanie modelového času (Client/Server) |
| **Obehy** | Import pracovného poriadku pre Turnusy (voliteľné) |
| **Export / import konfigurácie** | Záloha a obnovenie nastavení staníc |
| **Konfigurácia staníc** | Nastavenie jednotlivých staníc pre výpravcov |
| **Heslá** | Heslá pre Admin portal, Turnusy a jednotlivé stanice |

> [!IMPORTANT]
> Kroky relevantné pre prípravu akcie sú popísané v [INITIAL_SETUP.md](./INITIAL_SETUP.md).

---

### Import ZIP

Nahrajte `.zip` súbor s definíciou layoutu. Nahradí aktuálne aktívny layout. Postup vytvorenia súboru s layoutom nájdete v [INITIAL_SETUP.md](./INITIAL_SETUP.md).

> [!WARNING]
> Import nového ZIP resetuje všetky stavy vlakov a relácie výpravcov.

---

### Knižnica zvukov

Nahrajte vlastné zvuky upozornení (bežné audio formáty). Knižnica zobrazuje všetky nahrané súbory.

- **Predvolené upozornenie** – vyberte zvuk prehrávaný pri prichádzajúcej ponuke vlaku.
- Každý zvuk je možné prehrať (▶) a zmazať.
- Predvolený systémový zvuk nie je možné zmazať.

---

### Grafické cestovné poriadky

Nahrajte jeden alebo viac SVG súborov cestovných poriadkov. Nahrané cestovné poriadky budú dostupné v pohľade výpravcu. Každý súbor je možné zobraziť alebo zmazať.

---

### Správa stavu

#### Reset layoutu

Resetuje všetky stavy vlakov na začiatok dňa (čas 00:00). Všetky **dokončené** obehy sa znovu aktivujú. Použite po skončení prevádzkového dňa pre nový provoz s rovnakým layoutom.

#### Zmazať layout

Kompletne odstráni layout z DD-MB. Použite pri príprave novej akcie s iným layoutom.

---

### Čas relácie

Umožňuje prejsť na konkrétny modelový čas (formát `HH:MM`). Vlaky, ktorých čas odchodu uplynul pred cieľovým časom, sú automaticky označené ako **dokončené**.

---

### Modelový čas

Ovláda interné hodiny DD-MB. Nastavte počiatočný čas a rýchlosť prehrávania (0,5× – 4×).

---

### Synchronizácia času

| Režim | Správanie |
|---|---|
| **Vypnuté** | DD-MB používa iba vlastné interné hodiny |
| **Client** | DD-MB načúva externému vysielaniu a synchronizuje sa |
| **Server** | DD-MB vysiela vlastný čas do siete |

---

### Turnusy (voliteľné)

Importujte súbor `circulations.svg` exportovaný z nástroja Grafikon. Naplní portál **Turnusy** na priradenie strojvodcov k obehom.

Pozri [ROSTERS.md](./ROSTERS.md) pre podrobnosti o práci s Turnusmi.

---

### Export / import konfigurácie

- **Export všetkých** – stiahne konfiguráciu každej stanice ako `station-config.json`.
- **Import** – nahraný JSON sa okamžite aplikuje.

---

### Konfigurácia staníc

| Nastavenie | Popis |
|---|---|
| **Ľavý / pravý sused** | Susedné stanice v blokovom paneli výpravcu |
| **Sloty blokov** | Počet paralelných koľají medzi stanicami |
| **Skrytá** | Stanica je obsluhovaná automaticky |
| **Zjednodušená** | Stanica používa zjednodušený pohľad strojvodcu |
| **Cestovný poriadok** | Grafický cestovný poriadok pre túto stanicu |
| **Telefónne číslo** | Voliteľné telefónne číslo v záhlaví výpravcu |
| **Zvuk upozornenia** | Prepis predvoleného zvuku pre túto stanicu |
| **Heslo** | Vlastné prihlasovacie heslo pre výpravcu tejto stanice |

---

### Heslá

- **Heslo admina** – chráni Admin Panel.
- **Heslo Turnusov** – chráni portál Turnusy.
- **Heslá staníc** – nastavené v **Konfigurácii staníc** vyššie.

---

---

## Polski

### Przegląd

Panel administratora to centralne centrum zarządzania DD-MB. Dostępny z ekranu logowania przez zakładkę **Admin**.

Panel jest podzielony na następujące sekcje:

| Sekcja | Przeznaczenie |
|---|---|
| **Import ZIP** | Przesłanie pliku ZIP z układem torów |
| **Biblioteka dźwięków** | Przesyłanie i zarządzanie dźwiękami alertów |
| **Graficzne rozkłady jazdy** | Przesyłanie plików SVG rozkładów (opcjonalne) |
| **Zarządzanie stanem** | Resetuj lub usuń bieżący układ |
| **Czas sesji** | Oznacz pociągi jako zakończone do docelowego czasu |
| **Czas modelowy** | Sterowanie wewnętrznym zegarem |
| **Synchronizacja czasu** | Odbiór lub nadawanie czasu modelowego (Client/Server) |
| **Obiegi** | Import grafiku pracy dla Turnusów (opcjonalne) |
| **Eksport / import konfiguracji** | Kopia zapasowa i przywrócenie ustawień stacji |
| **Konfiguracja stacji** | Ustawienia poszczególnych stacji dla dyżurnych |
| **Hasła** | Hasła do panelu Admin, Turnusów i poszczególnych stacji |

> [!IMPORTANT]
> Kroki dotyczące przygotowania imprezy opisano w [INITIAL_SETUP.md](./INITIAL_SETUP.md).

---

### Import ZIP

Prześlij plik `.zip` z definicją układu torów. Zastępuje aktualnie aktywny układ. Sposób tworzenia pliku układu opisano w [INITIAL_SETUP.md](./INITIAL_SETUP.md).

> [!WARNING]
> Import nowego ZIP resetuje wszystkie stany pociągów i sesje dyżurnych.

---

### Biblioteka dźwięków

Przesyłaj własne dźwięki alertów (popularne formaty audio). Biblioteka wyświetla wszystkie przesłane pliki.

- **Domyślny alert** – wybierz dźwięk odtwarzany przy nowej ofercie pociągu.
- Każdy dźwięk można odtworzyć (▶) i usunąć.
- Domyślnego dźwięku systemowego nie można usunąć.

---

### Graficzne rozkłady jazdy

Prześlij jeden lub więcej plików SVG z rozkładami jazdy. Staną się dostępne w widoku dyżurnego. Każdy plik można podejrzeć lub usunąć.

---

### Zarządzanie stanem

#### Resetuj układ

Resetuje wszystkie stany pociągów do początku dnia (godzina 00:00). Wszystkie **ukończone** obiegi są ponownie aktywowane. Używaj po zakończeniu dnia operacyjnego.

#### Usuń układ

Całkowicie usuwa układ z DD-MB. Używaj przy przygotowaniu nowej imprezy z innym układem.

---

### Czas sesji

Umożliwia przejście do konkretnego czasu modelowego (format `HH:MM`). Pociągi, których czas odjazdu upłynął przed docelowym czasem, są automatycznie oznaczane jako **zakończone**.

---

### Czas modelowy

Steruje wewnętrznym zegarem DD-MB. Ustaw czas startowy i prędkość odtwarzania (0,5× – 4×).

---

### Synchronizacja czasu

| Tryb | Działanie |
|---|---|
| **Wyłączone** | DD-MB używa tylko własnego zegara wewnętrznego |
| **Client** | DD-MB nasłuchuje zewnętrznego źródła czasu i synchronizuje się |
| **Server** | DD-MB nadaje własny czas do sieci |

---

### Turnusy (opcjonalne)

Zaimportuj plik `circulations.svg` eksportowany z narzędzia Grafikon. Wypełni portal **Turnusy** umożliwiając przypisanie maszynistów do obiegów.

Zobacz [ROSTERS.md](./ROSTERS.md) po szczegóły dotyczące pracy z Turnusami.

---

### Eksport / import konfiguracji

- **Eksportuj wszystkie** – pobiera konfigurację każdej stacji jako `station-config.json`.
- **Import** – przesłany JSON jest natychmiast stosowany.

---

### Konfiguracja stacji

| Ustawienie | Opis |
|---|---|
| **Lewy / prawy sąsiad** | Sąsiednie stacje w panelu blokowym dyżurnego |
| **Sloty bloków** | Liczba równoległych torów między stacjami |
| **Ukryta** | Stacja jest obsługiwana automatycznie |
| **Uproszczona** | Stacja używa uproszczonego widoku maszynisty |
| **Rozkład jazdy** | Graficzny rozkład jazdy dla tej stacji |
| **Numer telefonu** | Opcjonalny numer w nagłówku dyżurnego |
| **Dźwięk alertu** | Nadpisanie domyślnego dźwięku dla tej stacji |
| **Hasło** | Własne hasło logowania dla dyżurnego tej stacji |

---

### Hasła

- **Hasło administratora** – chroni Panel administratora.
- **Hasło Turnusów** – chroni portal Turnusów.
- **Hasła stacji** – ustawiane w **Konfiguracji stacji** powyżej.

---

---

## Deutsch

### Übersicht

Das Admin-Panel ist die zentrale Steueroberfläche von DD-MB. Es ist über den Login-Bildschirm unter der Registerkarte **Admin** erreichbar.

Das Panel ist in folgende Abschnitte unterteilt:

| Abschnitt | Zweck |
|---|---|
| **ZIP importieren** | Layout-ZIP-Datei hochladen |
| **Soundbibliothek** | Alarmsounds hochladen und verwalten |
| **Grafische Fahrpläne** | SVG-Fahrpläne hochladen (optional) |
| **Statusverwaltung** | Aktuelles Layout zurücksetzen oder löschen |
| **Sitzungszeit** | Züge bis zu einem Zielzeitpunkt als erledigt markieren |
| **Modellzeit** | Steuerung der internen Uhr |
| **Zeitsynchronisation** | Modellzeit empfangen oder senden (Client/Server) |
| **Umläufe** | Import des Dienstplans für das Turnusse-Portal (optional) |
| **Konfiguration exportieren / importieren** | Sicherung und Wiederherstellung der Stationskonfiguration |
| **Stationskonfiguration** | Einstellungen je Station für Fahrdienstleiter |
| **Passwörter** | Passwörter für Admin-Portal, Turnusse und einzelne Stationen |

> [!IMPORTANT]
> Schritte zur Vorbereitung einer Veranstaltung sind in [INITIAL_SETUP.md](./INITIAL_SETUP.md) beschrieben.

---

### ZIP importieren

Laden Sie eine `.zip`-Datei mit der Layout-Definition hoch. Sie ersetzt das aktuell aktive Layout. Wie die Layout-Datei erstellt wird, ist in [INITIAL_SETUP.md](./INITIAL_SETUP.md) beschrieben.

> [!WARNING]
> Ein neuer ZIP-Import setzt alle Zugzustände und Fahrdienstleiter-Sitzungen zurück.

---

### Soundbibliothek

Laden Sie eigene Alarmsounds hoch (gängige Audioformate). Die Bibliothek zeigt alle hochgeladenen Dateien.

- **Standard-Alarm** – wählen Sie den Ton, der bei einem eingehenden Zugangebot abgespielt wird.
- Jeder Ton kann abgespielt (▶) und gelöscht werden.
- Der eingebaute Standardton kann nicht gelöscht werden.

---

### Grafische Fahrpläne

Laden Sie eine oder mehrere SVG-Fahrplandateien hoch. Sie stehen danach im Fahrdienstleiter-Fenster zur Verfügung. Jede Datei kann im Browser angezeigt oder gelöscht werden.

---

### Statusverwaltung

#### Layout zurücksetzen

Setzt alle Zugzustände auf den Tagesbeginn (00:00 Uhr) zurück. Alle **abgeschlossenen** Umläufe werden wieder aktiviert. Verwenden Sie dies nach Abschluss des Betriebstages.

#### Layout löschen

Entfernt das Layout vollständig aus DD-MB. Verwenden Sie dies bei der Vorbereitung einer neuen Veranstaltung mit einem anderen Layout.

---

### Sitzungszeit

Ermöglicht das Vorrücken auf eine bestimmte Modellzeit (Format `HH:MM`). Züge, deren Abfahrtszeit vor der Zielzeit liegt, werden automatisch als **erledigt** markiert.

---

### Modellzeit

Steuert die interne Uhr von DD-MB. Stellen Sie Startzeit und Wiedergabegeschwindigkeit (0,5× – 4×) ein.

---

### Zeitsynchronisation

| Modus | Verhalten |
|---|---|
| **Aus** | DD-MB verwendet nur die eigene interne Uhr |
| **Client** | DD-MB lauscht auf eine externe Zeitquelle und synchronisiert sich |
| **Server** | DD-MB sendet seine eigene Zeit ins Netzwerk |

---

### Turnusse (optional)

Importieren Sie eine `circulations.svg`-Datei, die aus dem Grafikon-Tool exportiert wurde. Befüllt das **Turnusse**-Portal zur Zuweisung von Triebfahrzeugführern zu Umläufen.

Siehe [ROSTERS.md](./ROSTERS.md) für Details zur Arbeit mit Turnussen.

---

### Konfiguration exportieren / importieren

- **Alle exportieren** – lädt die Konfiguration jeder Station als `station-config.json` herunter.
- **Importieren** – hochgeladene JSON wird sofort angewendet.

---

### Stationskonfiguration

| Einstellung | Beschreibung |
|---|---|
| **Linke / rechte Nachbarn** | Nachbarstationen im Block-Panel des Fahrdienstleiters |
| **Blockslots** | Anzahl paralleler Gleise zwischen Stationen |
| **Versteckt** | Station wird automatisch bedient |
| **Vereinfacht** | Station verwendet die vereinfachte Triebfahrzeugführer-Ansicht |
| **Fahrplan** | Grafischer Fahrplan für diese Station |
| **Telefonnummer** | Optionale Telefonnummer in der Kopfzeile |
| **Alarmsound** | Überschreiben des Standard-Alarmtons für diese Station |
| **Passwort** | Eigenes Login-Passwort für den Fahrdienstleiter dieser Station |

---

### Passwörter

- **Admin-Passwort** – schützt das Admin-Panel.
- **Turnusse-Passwort** – schützt das Turnusse-Portal.
- **Stationspasswörter** – werden in der **Stationskonfiguration** oben festgelegt.

---

---

## Magyar

### Áttekintés

Az Admin Panel a DD-MB központi vezérlőfelülete. A bejelentkezési képernyőn az **Admin** fülön érhető el.

A panel a következő szekciókra oszlik:

| Szekció | Funkció |
|---|---|
| **ZIP importálása** | Layout ZIP-fájl feltöltése |
| **Hangkönyvtár** | Figyelmeztető hangok feltöltése és kezelése |
| **Grafikus menetrendek** | SVG menetrend-fájlok feltöltése (opcionális) |
| **Állapotkezelés** | Az aktuális layout visszaállítása vagy törlése |
| **Munkamenet-idő** | Vonatok befejezettnek jelölése egy célpont időpontig |
| **Modellszemléleti idő** | Belső óra vezérlése |
| **Időszinkronizálás** | Modellidő fogadása vagy sugárzása (Client/Server) |
| **Forgalmi rendek** | Szolgálati menetrend importálása a Turnuszokhoz (opcionális) |
| **Konfiguráció exportálása / importálása** | Állomásbeállítások mentése és visszaállítása |
| **Állomáskonfiguráció** | Egyedi beállítások forgalmi szolgálatosoknak |
| **Jelszavak** | Jelszavak az Admin portálhoz, a Turnuszokhoz és az egyes állomásokhoz |

> [!IMPORTANT]
> Az eseményelőkészítéssel kapcsolatos lépések az [INITIAL_SETUP.md](./INITIAL_SETUP.md) fájlban találhatók.

---

### ZIP importálása

Töltsön fel egy `.zip` fájlt a layout definíciójával. Ez felváltja a jelenleg aktív layoutot. A layout fájl létrehozásának menetéért lásd: [INITIAL_SETUP.md](./INITIAL_SETUP.md).

> [!WARNING]
> Az új ZIP importálása visszaállítja az összes vonat állapotát és a forgalmi szolgálatos munkameneteket.

---

### Hangkönyvtár

Töltsön fel egyedi figyelmeztető hangokat (közös audioformátumok). A könyvtár az összes feltöltött fájlt listázza.

- **Alapértelmezett riasztás** – válassza ki a bejövő vonatajánlatkor lejátszott hangot.
- Minden hang lejátszható (▶) és törölhető.
- A beépített alapértelmezett hang nem törölhető.

---

### Grafikus menetrendek

Töltsön fel egy vagy több SVG menetrend-fájlt. Ezek elérhetővé válnak a forgalmi szolgálatos nézetben. Minden fájl megtekinthető és törölhető.

---

### Állapotkezelés

#### Layout visszaállítása

Visszaállítja az összes vonatallapotot a nap elejére (00:00). Minden **befejezett** forgalmi rend újra aktívvá válik. Az üzemi nap lezárása után használja.

#### Layout törlése

Teljesen eltávolítja a layoutot a DD-MB-ből. Különböző layouttal tartott új esemény előkészítésekor használja.

---

### Munkamenet-idő

Lehetővé teszi egy adott modellidőre (formátum: `HH:MM`) való ugrást. Az indulási idejüket az adott idő előtt teljesítő vonatok automatikusan **befejezettnek** jelölődnek.

---

### Modellszemléleti idő

A DD-MB belső óráját vezérli. Állítsa be a kezdési időt és a lejátszási sebességet (0,5× – 4×).

---

### Időszinkronizálás

| Mód | Viselkedés |
|---|---|
| **Ki** | A DD-MB csak a saját belső óráját használja |
| **Client** | A DD-MB külső időforrásra figyel és szinkronizál |
| **Server** | A DD-MB saját idejét sugározza a hálózatra |

---

### Turnuszok (opcionális)

Importáljon egy `circulations.svg` fájlt, amelyet a Grafikon eszközből exportált. Ez feltölti a **Turnuszok** portált a mozdonyvezető–forgalmi rend párosítások kezeléséhez.

Lásd: [ROSTERS.md](./ROSTERS.md) a Turnuszok használatának részleteiért.

---

### Konfiguráció exportálása / importálása

- **Összes exportálása** – minden állomás konfigurációját `station-config.json` fájlként tölti le.
- **Importálás** – a feltöltött JSON azonnal érvénybe lép.

---

### Állomáskonfiguráció

| Beállítás | Leírás |
|---|---|
| **Bal / jobb szomszédok** | Szomszéd állomások a forgalmi szolgálatos blokkpaneljén |
| **Blokkhelyek** | Párhuzamos vágányok száma az állomások között |
| **Rejtett** | Az állomást automatikusan kezeli a rendszer |
| **Egyszerűsített** | Az állomás az egyszerűsített mozdonyvezető-nézetet használja |
| **Menetrend** | Grafikus menetrend ehhez az állomáshoz |
| **Telefonszám** | Opcionális telefonszám a fejlécben |
| **Figyelmeztető hang** | Alapértelmezett hang felülírása erre az állomásra |
| **Jelszó** | Egyedi bejelentkezési jelszó az állomás forgalmi szolgálatosának |

---

### Jelszavak

- **Admin jelszó** – védi az Admin Panelt.
- **Turnuszok jelszava** – védi a Turnuszok portált.
- **Állomásjelszavak** – az **Állomáskonfigurációban** állíthatók be fent.
