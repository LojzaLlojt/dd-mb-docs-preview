# DD-MB — Dopravní deník, Moduly Brno

---

- [English (EN)](#english)
- [Čeština (CZ)](#čeština)
- [Slovenčina (SK)](#slovenčina)
- [Polski (PL)](#polski)
- [Deutsch (DE)](#deutsch)
- [Magyar (HU)](#magyar)

---

---

## English

**DD-MB** is a Computer-Assisted Train Notification (dispatch) system for modular model railroad operations. It runs as a self-hosted web application and lets stations communicate train movements in real time — ideal for club layouts, modular meets, and multi-station model railway sessions.

A dispatcher operates station, manages train offers, incoming/outgoing trains and follows graphical timetables. A separate, simplified driver view is available for end stations, designed for quick, low-friction operation by a train's "driver."

### Features

- **Real-time dispatch** between stations over a local network (Socket.IO), with no internet connection required to operate.
- **Dispatcher view** — blocks, incoming/outgoing train offers, pass-through and extra trains, train notes/freight info, rejection handling, and more.
- **Simplified driver view** — a streamlined interface for end stations: confirm arrivals, offer/retract trains, ring adjacent stations, and manage multiple simultaneous trains.
- **Graphical timetables** for planning and following scheduled circulations.
- **Rosters** — assign drivers to circulations, prepare the next model day in advance, and track driver/roster statistics.
- **Admin panel** — manage stations, timetables, users, and other server-wide settings, including layout import/export.
- **Multi-language UI** — English, Čeština, Slovenčina, Polski, Deutsch, and Magyar.
- **Light and dark themes.**

### Repository Layout

```
src/backend/    Node.js/Express + Socket.IO server (dispatch logic, state, REST API)
src/frontend/   React + Vite + Tailwind CSS single-page application
e2e/            Playwright end-to-end tests
docs/           User and admin documentation (multi-language)
timetables/     Sample/exported timetable data
sounds/         Notification sound assets
install.sh / install.bat   Platform install scripts
start.sh / start.bat       Platform start scripts
```

### Getting Started

1. Download the latest release from the **Releases** page, or clone this repository.
2. Run `install.sh` (macOS/Linux) or `install.bat` (Windows) — this installs Node.js if needed and all dependencies.
3. Run `start.sh` (macOS/Linux) or `start.bat` (Windows) to launch the server.
4. Open the printed URL in a browser on each station's device.

> **Note:** To use DD-MB during a railway session, every station needs a device with a web browser (e.g. a laptop, tablet, or phone) connected to the same network as the server.

For detailed requirements, manual setup, and troubleshooting, see the **[Installation Guide](./docs/INSTALL.md)**.

#### Development

```sh
npm run install:all      # install root, backend, and frontend dependencies
npm run dev:backend      # start backend in dev mode
npm run dev:frontend     # start frontend dev server (Vite)
npm run build:frontend   # build frontend for production
npm start                # run the production backend
npm test                 # run backend unit tests
npm run test:e2e         # run Playwright end-to-end tests
```

### Documentation

Full documentation lives in **[docs/](./docs/README.md)** and is available in English, Čeština, Slovenčina, Polski, Deutsch, and Magyar:

- **[Installation Guide](./docs/INSTALL.md)** — installing and running the server.
- **[Initial Setup Guide](./docs/INITIAL_SETUP.md)** — first steps after installation: creating stations, users, and the layout.
- **[Dispatcher](./docs/DISPATCHER.md)** — the main dispatcher view and its features.
- **[Simplified Driver View](./docs/SIMPLIFIED.md)** — the simplified end-station view for drivers.
- **[Admin Panel](./docs/ADMIN.md)** — administration of stations, timetables, and settings.
- **[Rosters](./docs/ROSTERS.md)** — assigning drivers and tracking roster statistics.

See **[CHANGELOG.md](./CHANGELOG.md)** for release history.

### License

See **[LICENSE.md](./LICENSE.md)** for license terms, and **[CREDITS.md](./CREDITS.md)** for third-party open-source libraries used by this project.

---

---

## Čeština

**DD-MB** je systém počítačem asistované výpravy vlaků (Computer-Assisted Train Notification) pro provoz modulové modelové železnice. Běží jako webová aplikace a umožňuje stanicím komunikovat pohyby vlaků v reálném čase — ideální pro klubová kolejiště, modulová setkání i vícestaniční modelové provozy.

Výpravčí obsluhuje stanici, spravuje nabídky vlaků, příchozí/odchozí vlaky a sleduje grafické jízdní řády. Pro koncové stanice je k dispozici samostatný zjednodušený pohled strojvedoucího, navržený pro rychlou obsluhu s minimem kroků.

### Funkce

- **Výprava v reálném čase** mezi stanicemi přes lokální síť (Socket.IO), bez nutnosti internetového připojení za provozu.
- **Pohled výpravčího** — bloky, příchozí/odchozí nabídky vlaků, průjezdné a mimořádné vlaky, poznámky k vlaku/informace o nákladu, obsluha odmítnutí a další.
- **Zjednodušený pohled strojvedoucího** — zjednodušené rozhraní pro koncové stanice: potvrzení příjezdu, nabízení/stažení vlaku, zazvonění sousední stanici a správa více souběžných vlaků.
- **Grafické jízdní řády** pro plánování a sledování plánovaných oběhů.
- **Turnusy** — přiřazování strojvedoucích k oběhům, příprava dalšího modelového dne dopředu a sledování statistik strojvedoucích a turnusů.
- **Administrace** — správa stanic, jízdních řádů, uživatelů a dalších celoserverových nastavení, včetně importu/exportu kolejiště.
- **Vícejazyčné rozhraní** — angličtina, čeština, slovenština, polština, němčina a maďarština.
- **Světlý i tmavý motiv.**

### Struktura repozitáře

```
src/backend/    Node.js/Express + Socket.IO server (logika výpravy, stav, REST API)
src/frontend/   Aplikace React + Vite + Tailwind CSS
e2e/            End-to-end testy Playwright
docs/           Uživatelská a administrátorská dokumentace (vícejazyčná)
timetables/     Ukázková/exportovaná data jízdních řádů
sounds/         Zvukové soubory upozornění
install.sh / install.bat   Instalační skripty pro jednotlivé platformy
start.sh / start.bat       Spouštěcí skripty pro jednotlivé platformy
```

### Začínáme

1. Stáhněte nejnovější verzi ze sekce „Releases“ na GitHubu, nebo naklonujte tento repozitář.
2. Spusťte `install.sh` (macOS/Linux) nebo `install.bat` (Windows) — tím se podle potřeby nainstaluje Node.js a všechny závislosti.
3. Spusťte `start.sh` (macOS/Linux) nebo `start.bat` (Windows) pro spuštění serveru.
4. Na zařízení každé stanice otevřete v prohlížeči vypsanou adresu.

> **Poznámka:** Pro použití DD-MB při provozu na kolejišti potřebuje každá stanice zařízení s webovým prohlížečem (např. notebook, tablet nebo telefon) připojené do stejné sítě jako server.

Podrobné požadavky, ruční instalaci a řešení problémů najdete v **[Instalační příručce](./docs/INSTALL.md)**.

#### Vývoj

```sh
npm run install:all      # instalace závislostí v kořeni, backendu a frontendu
npm run dev:backend      # spuštění backendu ve vývojovém režimu
npm run dev:frontend     # spuštění vývojového serveru frontendu (Vite)
npm run build:frontend   # sestavení frontendu pro produkci
npm start                # spuštění produkčního backendu
npm test                 # spuštění unit testů backendu
npm run test:e2e         # spuštění end-to-end testů Playwright
```

### Dokumentace

Kompletní dokumentace je v **[docs/](./docs/README.md)** a je dostupná v angličtině, češtině, slovenčině, polštině, němčině a maďarštině:

- **[Instalační příručka](./docs/INSTALL.md)** — instalace a spuštění serveru.
- **[Průvodce prvotním nastavením](./docs/INITIAL_SETUP.md)** — první kroky po instalaci: vytvoření stanic, uživatelů a kolejiště.
- **[Výpravčí](./docs/DISPATCHER.md)** — hlavní pohled výpravčího a jeho funkce.
- **[Zjednodušený pohled strojvedoucího](./docs/SIMPLIFIED.md)** — zjednodušený pohled pro koncové stanice určený strojvedoucím.
- **[Administrace](./docs/ADMIN.md)** — správa stanic, jízdních řádů a nastavení.
- **[Turnusy](./docs/ROSTERS.md)** — přiřazování strojvedoucích a sledování statistik turnusů.

Historii verzí najdete v **[CHANGELOG.md](./CHANGELOG.md)**.

### Licence

Licenční podmínky najdete v **[LICENSE.md](./LICENSE.md)** a seznam použitých open-source knihoven třetích stran v **[CREDITS.md](./CREDITS.md)**.

---

---

## Slovenčina

**DD-MB** je systém počítačom asistovanej výpravy vlakov (Computer-Assisted Train Notification) pre prevádzku modulovej modelovej železnice. Beží ako webová aplikácia a umožňuje staniciam komunikovať pohyby vlakov v reálnom čase — ideálne pre klubové koľajiská, modulové stretnutia i viacstaničné modelové prevádzky.

Výpravca obsluhuje stanicu, spravuje ponuky vlakov, prichádzajúce/odchádzajúce vlaky a sleduje grafické cestovné poriadky. Pre koncové stanice je k dispozícii samostatný zjednodušený pohľad rušňovodiča, navrhnutý pre rýchlu obsluhu s minimom krokov.

### Funkcie

- **Výprava v reálnom čase** medzi stanicami cez lokálnu sieť (Socket.IO), bez potreby internetového pripojenia počas prevádzky.
- **Pohľad výpravcu** — bloky, prichádzajúce/odchádzajúce ponuky vlakov, prejazdné a mimoriadne vlaky, poznámky k vlaku/informácie o náklade, obsluha odmietnutia a ďalšie.
- **Zjednodušený pohľad rušňovodiča** — zjednodušené rozhranie pre koncové stanice: potvrdenie príchodu, ponúkanie/stiahnutie vlaku, zazvonenie susednej stanici a správa viacerých súbežných vlakov.
- **Grafické cestovné poriadky** na plánovanie a sledovanie plánovaných obehov.
- **Turnusy** — priraďovanie rušňovodičov k obehom, príprava ďalšieho modelového dňa vopred a sledovanie štatistík rušňovodičov a turnusov.
- **Administrácia** — správa staníc, cestovných poriadkov, používateľov a ďalších celoserverových nastavení, vrátane importu/exportu koľajiska.
- **Viacjazyčné rozhranie** — angličtina, čeština, slovenčina, poľština, nemčina a maďarčina.
- **Svetlý aj tmavý motív.**

### Štruktúra repozitára

```
src/backend/    Node.js/Express + Socket.IO server (logika výpravy, stav, REST API)
src/frontend/   Aplikácia React + Vite + Tailwind CSS
e2e/            End-to-end testy Playwright
docs/           Používateľská a administrátorská dokumentácia (viacjazyčná)
timetables/     Ukážkové/exportované dáta cestovných poriadkov
sounds/         Zvukové súbory upozornení
install.sh / install.bat   Inštalačné skripty pre jednotlivé platformy
start.sh / start.bat       Spúšťacie skripty pre jednotlivé platformy
```

### Začíname

1. Stiahnite najnovšiu verziu zo sekcie „Releases“ na GitHube, alebo naklonujte tento repozitár.
2. Spustite `install.sh` (macOS/Linux) alebo `install.bat` (Windows) — tým sa podľa potreby nainštaluje Node.js a všetky závislosti.
3. Spustite `start.sh` (macOS/Linux) alebo `start.bat` (Windows) na spustenie servera.
4. Na zariadení každej stanice otvorte v prehliadači vypísanú adresu.

> **Poznámka:** Na použitie DD-MB počas prevádzky na koľajisku potrebuje každá stanica zariadenie s webovým prehliadačom (napr. notebook, tablet alebo telefón) pripojené do rovnakej siete ako server.

Podrobné požiadavky, manuálnu inštaláciu a riešenie problémov nájdete v **[Inštalačnej príručke](./docs/INSTALL.md)**.

#### Vývoj

```sh
npm run install:all      # inštalácia závislostí v koreni, backende a frontende
npm run dev:backend      # spustenie backendu vo vývojovom režime
npm run dev:frontend     # spustenie vývojového servera frontendu (Vite)
npm run build:frontend   # zostavenie frontendu pre produkciu
npm start                # spustenie produkčného backendu
npm test                 # spustenie unit testov backendu
npm run test:e2e         # spustenie end-to-end testov Playwright
```

### Dokumentácia

Kompletná dokumentácia je v **[docs/](./docs/README.md)** a je dostupná v angličtine, češtine, slovenčine, poľštine, nemčine a maďarčine:

- **[Inštalačná príručka](./docs/INSTALL.md)** — inštalácia a spustenie servera.
- **[Sprievodca prvotným nastavením](./docs/INITIAL_SETUP.md)** — prvé kroky po inštalácii: vytvorenie staníc, používateľov a koľajiska.
- **[Výpravca](./docs/DISPATCHER.md)** — hlavný pohľad výpravcu a jeho funkcie.
- **[Zjednodušený pohľad rušňovodiča](./docs/SIMPLIFIED.md)** — zjednodušený pohľad pre koncové stanice určený rušňovodičom.
- **[Administrácia](./docs/ADMIN.md)** — správa staníc, cestovných poriadkov a nastavení.
- **[Turnusy](./docs/ROSTERS.md)** — priraďovanie rušňovodičov a sledovanie štatistík turnusov.

Históriu verzií nájdete v **[CHANGELOG.md](./CHANGELOG.md)**.

### Licencia

Licenčné podmienky nájdete v **[LICENSE.md](./LICENSE.md)** a zoznam použitých open-source knižníc tretích strán v **[CREDITS.md](./CREDITS.md)**.

---

---

## Polski

**DD-MB** to system wspomaganej komputerowo sygnalizacji ruchu pociągów (Computer-Assisted Train Notification) do obsługi modułowej kolei modelowej. Działa jako aplikacja webowa i pozwala stacjom komunikować ruchy pociągów w czasie rzeczywistym — idealne dla układów klubowych, spotkań modułowych i sesji z wieloma stacjami.

Dyżurny ruchu obsługuje stację, zarządza ofertami pociągów, pociągami przychodzącymi/wychodzącymi oraz śledzi graficzne rozkłady jazdy. Dla stacji końcowych dostępny jest osobny, uproszczony widok maszynisty, zaprojektowany do szybkiej obsługi przy minimalnej liczbie kroków.

### Funkcje

- **Dyspozycja w czasie rzeczywistym** między stacjami w sieci lokalnej (Socket.IO), bez potrzeby połączenia internetowego podczas pracy.
- **Widok dyżurnego ruchu** — bloki, oferty pociągów przychodzące/wychodzące, pociągi przejazdowe i dodatkowe, uwagi do pociągu/informacje o ładunku, obsługa odrzuceń i inne.
- **Uproszczony widok maszynisty** — uproszczony interfejs dla stacji końcowych: potwierdzanie przyjazdu, oferowanie/wycofywanie pociągu, dzwonienie do sąsiedniej stacji i obsługa wielu jednoczesnych pociągów.
- **Graficzne rozkłady jazdy** do planowania i śledzenia zaplanowanych obiegów.
- **Turnusy** — przypisywanie maszynistów do obiegów, przygotowywanie kolejnego dnia modelowego z wyprzedzeniem oraz śledzenie statystyk maszynistów i turnusów.
- **Panel administracyjny** — zarządzanie stacjami, rozkładami jazdy, użytkownikami i innymi ustawieniami serwera, w tym import/eksport układu.
- **Wielojęzyczny interfejs** — angielski, czeski, słowacki, polski, niemiecki i węgierski.
- **Jasny i ciemny motyw.**

### Struktura repozytorium

```
src/backend/    Serwer Node.js/Express + Socket.IO (logika dyspozycji, stan, REST API)
src/frontend/   Aplikacja React + Vite + Tailwind CSS
e2e/            Testy end-to-end Playwright
docs/           Dokumentacja użytkownika i administratora (wielojęzyczna)
timetables/     Przykładowe/wyeksportowane dane rozkładów jazdy
sounds/         Pliki dźwiękowe powiadomień
install.sh / install.bat   Skrypty instalacyjne dla poszczególnych platform
start.sh / start.bat       Skrypty uruchamiające dla poszczególnych platform
```

### Pierwsze kroki

1. Pobierz najnowsze wydanie z sekcji „Releases” na GitHubie lub sklonuj to repozytorium.
2. Uruchom `install.sh` (macOS/Linux) lub `install.bat` (Windows) — zainstaluje to Node.js (jeśli potrzeba) i wszystkie zależności.
3. Uruchom `start.sh` (macOS/Linux) lub `start.bat` (Windows), aby uruchomić serwer.
4. Otwórz wyświetlony adres w przeglądarce na urządzeniu każdej stacji.

> **Uwaga:** Aby korzystać z DD-MB podczas sesji na kolei, każda stacja potrzebuje urządzenia z przeglądarką internetową (np. laptopa, tabletu lub telefonu) podłączonego do tej samej sieci co serwer.

Szczegółowe wymagania, ręczną instalację i rozwiązywanie problemów znajdziesz w **[Instrukcji instalacji](./docs/INSTALL.md)**.

#### Rozwój

```sh
npm run install:all      # instalacja zależności w katalogu głównym, backendzie i frontendzie
npm run dev:backend      # uruchomienie backendu w trybie deweloperskim
npm run dev:frontend     # uruchomienie serwera deweloperskiego frontendu (Vite)
npm run build:frontend   # budowanie frontendu do produkcji
npm start                # uruchomienie produkcyjnego backendu
npm test                 # uruchomienie testów jednostkowych backendu
npm run test:e2e         # uruchomienie testów end-to-end Playwright
```

### Dokumentacja

Pełna dokumentacja znajduje się w **[docs/](./docs/README.md)** i jest dostępna w języku angielskim, czeskim, słowackim, polskim, niemieckim i węgierskim:

- **[Instrukcja instalacji](./docs/INSTALL.md)** — instalacja i uruchamianie serwera.
- **[Przewodnik po konfiguracji początkowej](./docs/INITIAL_SETUP.md)** — pierwsze kroki po instalacji: tworzenie stacji, użytkowników i układu.
- **[Dyżurny ruchu](./docs/DISPATCHER.md)** — główny widok dyżurnego ruchu i jego funkcje.
- **[Uproszczony widok maszynisty](./docs/SIMPLIFIED.md)** — uproszczony widok dla stacji końcowych, przeznaczony dla maszynistów.
- **[Panel administracyjny](./docs/ADMIN.md)** — zarządzanie stacjami, rozkładami jazdy i ustawieniami.
- **[Turnusy](./docs/ROSTERS.md)** — przypisywanie maszynistów i śledzenie statystyk turnusów.

Historia wydań znajduje się w **[CHANGELOG.md](./CHANGELOG.md)**.

### Licencja

Warunki licencji znajdują się w **[LICENSE.md](./LICENSE.md)**, a lista wykorzystanych bibliotek open source stron trzecich w **[CREDITS.md](./CREDITS.md)**.

---

---

## Deutsch

**DD-MB** ist ein computergestütztes Zugmeldesystem (Computer-Assisted Train Notification) für den Betrieb modularer Modelleisenbahnen. Es läuft als Webanwendung und ermöglicht Stationen, Zugbewegungen in Echtzeit zu kommunizieren — ideal für Vereinsanlagen, Modultreffen und Sitzungen mit mehreren Stationen.

Ein Fahrdienstleiter bedient die Station, verwaltet Zugangebote, ankommende/abgehende Züge und folgt grafischen Fahrplänen. Für Endstationen steht eine separate, vereinfachte Triebfahrzeugführer-Ansicht zur Verfügung, die für eine schnelle Bedienung mit minimalem Aufwand ausgelegt ist.

### Funktionen

- **Echtzeit-Fahrdienst** zwischen Stationen über ein lokales Netzwerk (Socket.IO), ohne dass während des Betriebs eine Internetverbindung erforderlich ist.
- **Fahrdienstleiter-Ansicht** — Blöcke, ankommende/abgehende Zugangebote, durchfahrende und Sonderzüge, Zughinweise/Frachtinformationen, Behandlung von Ablehnungen und mehr.
- **Vereinfachte Triebfahrzeugführer-Ansicht** — eine schlanke Oberfläche für Endstationen: Bestätigen der Ankunft, Anbieten/Zurückziehen eines Zuges, Anrufen einer Nachbarstation und Verwaltung mehrerer gleichzeitiger Züge.
- **Grafische Fahrpläne** zur Planung und Verfolgung geplanter Umläufe.
- **Turnusse** — Zuweisung von Triebfahrzeugführern zu Umläufen, Vorbereitung des nächsten Modelltages im Voraus und Verfolgung von Fahrer- und Turnusstatistiken.
- **Admin-Bereich** — Verwaltung von Stationen, Fahrplänen, Benutzern und weiteren serverweiten Einstellungen, einschließlich Import/Export der Anlage.
- **Mehrsprachige Oberfläche** — Englisch, Tschechisch, Slowakisch, Polnisch, Deutsch und Ungarisch.
- **Heller und dunkler Modus.**

### Repository-Struktur

```
src/backend/    Node.js/Express + Socket.IO-Server (Fahrdienstlogik, Status, REST-API)
src/frontend/   React + Vite + Tailwind CSS Single-Page-Application
e2e/            Playwright End-to-End-Tests
docs/           Benutzer- und Administratordokumentation (mehrsprachig)
timetables/     Beispiel-/exportierte Fahrplandaten
sounds/         Benachrichtigungston-Dateien
install.sh / install.bat   Installationsskripte je Plattform
start.sh / start.bat       Startskripte je Plattform
```

### Erste Schritte

1. Laden Sie die neueste Version von der „Releases“-Seite herunter oder klonen Sie dieses Repository.
2. Führen Sie `install.sh` (macOS/Linux) oder `install.bat` (Windows) aus — dies installiert bei Bedarf Node.js und alle Abhängigkeiten.
3. Führen Sie `start.sh` (macOS/Linux) oder `start.bat` (Windows) aus, um den Server zu starten.
4. Öffnen Sie die ausgegebene Adresse im Browser auf dem Gerät jeder Station.

> **Hinweis:** Um DD-MB bei einer Betriebssitzung zu nutzen, benötigt jede Station ein Gerät mit Webbrowser (z. B. Laptop, Tablet oder Smartphone), das sich im selben Netzwerk wie der Server befindet.

Detaillierte Anforderungen, die manuelle Installation und Fehlerbehebung finden Sie in der **[Installationsanleitung](./docs/INSTALL.md)**.

#### Entwicklung

```sh
npm run install:all      # Abhängigkeiten im Root, Backend und Frontend installieren
npm run dev:backend      # Backend im Entwicklungsmodus starten
npm run dev:frontend     # Frontend-Entwicklungsserver starten (Vite)
npm run build:frontend   # Frontend für die Produktion bauen
npm start                # Produktions-Backend starten
npm test                 # Backend-Unit-Tests ausführen
npm run test:e2e         # Playwright End-to-End-Tests ausführen
```

### Dokumentation

Die vollständige Dokumentation befindet sich in **[docs/](./docs/README.md)** und ist auf Englisch, Tschechisch, Slowakisch, Polnisch, Deutsch und Ungarisch verfügbar:

- **[Installationsanleitung](./docs/INSTALL.md)** — Installation und Start des Servers.
- **[Ersteinrichtungsanleitung](./docs/INITIAL_SETUP.md)** — erste Schritte nach der Installation: Anlegen von Stationen, Benutzern und der Anlage.
- **[Fahrdienstleiter](./docs/DISPATCHER.md)** — die Hauptansicht des Fahrdienstleiters und ihre Funktionen.
- **[Vereinfachte Triebfahrzeugführer-Ansicht](./docs/SIMPLIFIED.md)** — die vereinfachte Endstations-Ansicht für Triebfahrzeugführer.
- **[Admin-Bereich](./docs/ADMIN.md)** — Verwaltung von Stationen, Fahrplänen und Einstellungen.
- **[Turnusse](./docs/ROSTERS.md)** — Zuweisung von Triebfahrzeugführern und Verfolgung von Turnusstatistiken.

Die Versionshistorie finden Sie in **[CHANGELOG.md](./CHANGELOG.md)**.

### Lizenz

Die Lizenzbedingungen finden Sie in **[LICENSE.md](./LICENSE.md)** und die Liste der verwendeten Open-Source-Bibliotheken Dritter in **[CREDITS.md](./CREDITS.md)**.

---

---

## Magyar

A **DD-MB** egy számítógéppel támogatott vonatértesítő (Computer-Assisted Train Notification) rendszer moduláris modellvasúti üzemeltetéshez. Webalkalmazásként fut, és lehetővé teszi, hogy az állomások valós időben kommunikálják a vonatmozgásokat — ideális klubpályákhoz, moduláris találkozókhoz és több állomásos modellvasúti üzemekhez.

A forgalomirányító kezeli az állomást, a vonatajánlatokat, az érkező/induló vonatokat, és követi a grafikus menetrendeket. A végállomásokhoz külön, egyszerűsített mozdonyvezetői nézet áll rendelkezésre, amelyet gyors, minimális lépésszámú kezelésre terveztek.

### Funkciók

- **Valós idejű forgalomirányítás** az állomások között helyi hálózaton (Socket.IO) keresztül, internetkapcsolat nélkül is üzemeltethető.
- **Forgalomirányítói nézet** — blokkok, érkező/induló vonatajánlatok, áthaladó és rendkívüli vonatok, vonatmegjegyzések/rakományinformációk, elutasítások kezelése és további funkciók.
- **Egyszerűsített mozdonyvezetői nézet** — letisztult felület a végállomásokhoz: érkezés megerősítése, vonat felajánlása/visszavonása, szomszéd állomás csengetése és több egyidejű vonat kezelése.
- **Grafikus menetrendek** a tervezett körforgások megtervezéséhez és követéséhez.
- **Turnusok** — mozdonyvezetők hozzárendelése körforgásokhoz, a következő modellnap előzetes előkészítése, valamint a mozdonyvezetői és turnusstatisztikák nyomon követése.
- **Admin panel** — állomások, menetrendek, felhasználók és egyéb szerverszintű beállítások kezelése, beleértve a pályahálózat importálását/exportálását.
- **Többnyelvű felhasználói felület** — angol, cseh, szlovák, lengyel, német és magyar.
- **Világos és sötét téma.**

### Repository felépítése

```
src/backend/    Node.js/Express + Socket.IO szerver (forgalomirányítási logika, állapot, REST API)
src/frontend/   React + Vite + Tailwind CSS egyoldalas alkalmazás
e2e/            Playwright end-to-end tesztek
docs/           Felhasználói és adminisztrátori dokumentáció (többnyelvű)
timetables/     Minta/exportált menetrend adatok
sounds/         Értesítési hangfájlok
install.sh / install.bat   Platformonkénti telepítőszkriptek
start.sh / start.bat       Platformonkénti indítószkriptek
```

### Kezdő lépések

1. Töltse le a legújabb kiadást a GitHub „Releases” részéből, vagy klónozza ezt a repository-t.
2. Futtassa az `install.sh` (macOS/Linux) vagy az `install.bat` (Windows) szkriptet — ez szükség esetén telepíti a Node.js-t és minden függőséget.
3. Futtassa a `start.sh` (macOS/Linux) vagy a `start.bat` (Windows) szkriptet a szerver elindításához.
4. Minden állomás eszközén nyissa meg a kiírt címet a böngészőben.

> **Megjegyzés:** A DD-MB üzemeltetési munkamenet alatti használatához minden állomásnak szüksége van egy webböngészővel rendelkező eszközre (pl. laptop, tablet vagy telefon), amely ugyanahhoz a hálózathoz csatlakozik, mint a szerver.

A részletes követelményekért, a manuális telepítésért és a hibaelhárításért lásd a **[Telepítési útmutatót](./docs/INSTALL.md)**.

#### Fejlesztés

```sh
npm run install:all      # függőségek telepítése a gyökérben, a backendben és a frontendben
npm run dev:backend      # backend indítása fejlesztői módban
npm run dev:frontend     # frontend fejlesztői szerver indítása (Vite)
npm run build:frontend   # frontend build készítése éles üzemhez
npm start                # éles backend indítása
npm test                 # backend unit tesztek futtatása
npm run test:e2e         # Playwright end-to-end tesztek futtatása
```

### Dokumentáció

A teljes dokumentáció a **[docs/](./docs/README.md)** mappában található, és elérhető angol, cseh, szlovák, lengyel, német és magyar nyelven:

- **[Telepítési útmutató](./docs/INSTALL.md)** — a szerver telepítése és indítása.
- **[Kezdeti beállítási útmutató](./docs/INITIAL_SETUP.md)** — első lépések a telepítés után: állomások, felhasználók és a pályahálózat létrehozása.
- **[Forgalomirányító](./docs/DISPATCHER.md)** — a forgalomirányító fő nézete és funkciói.
- **[Egyszerűsített mozdonyvezetői nézet](./docs/SIMPLIFIED.md)** — az egyszerűsített végállomás-nézet mozdonyvezetők számára.
- **[Admin panel](./docs/ADMIN.md)** — állomások, menetrendek és beállítások kezelése.
- **[Turnusok](./docs/ROSTERS.md)** — mozdonyvezetők hozzárendelése és a turnusstatisztikák nyomon követése.

A kiadási előzmények a **[CHANGELOG.md](./CHANGELOG.md)** fájlban találhatók.

### Licenc

A licencfeltételek a **[LICENSE.md](./LICENSE.md)** fájlban, a felhasznált harmadik féltől származó nyílt forráskódú könyvtárak listája pedig a **[CREDITS.md](./CREDITS.md)** fájlban található.
