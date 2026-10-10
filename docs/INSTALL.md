# DD-MB – Installation Guide

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

### Requirements

- **Node.js v20 or later** (npm is bundled with Node.js – no separate installation needed)
- Windows 10/11, macOS 10.15+, or Linux
- A modern web browser (Chrome, Firefox, Edge, Safari)
- An internet connection is required during installation so the system can download all necessary modules. Offline installations are not supported.

### Download

- Download latest release from "Releases" part on Github or clone repository.
- Extract zip to any folder where DD-MB should be started from.

### Installation

**Windows:**

1. Double-click `install.bat`
2. If Node.js is not installed, the script will attempt to install it automatically via **winget** (built into Windows 10 1709+ and Windows 11). If winget is not available, follow the on-screen instructions to install Node.js manually from [https://nodejs.org](https://nodejs.org).
3. After a successful installation, the script prints **"Installation complete!"**

**macOS / Linux:**

1. Open a Terminal in the project folder
2. Run:

   ```sh
   chmod +x install.sh
   ./install.sh
   ```

3. On macOS, if Node.js is missing, the script installs it via **Homebrew**. If Homebrew is not installed, follow the on-screen instructions.
4. On Linux, the script installs Node.js via **NodeSource** (requires `curl` and `sudo`).
5. After a successful installation, the script prints **"Installation complete!"**

### Starting the application

**Windows:** Double-click `start.bat`

**macOS / Linux:**

```sh
./start.sh
```

Then open your browser at: **http://localhost:3000**

### Default credentials

| Role | Username | Password |
| ---- | -------- | -------- |
| Admin | `admin` | `admin123` |
| Dispatcher | station name (from dropdown) | lowercase station name without diacritics |
| Rosters | `roster` | `rosters` |

To change the admin password set the `ADMIN_PASSWORD` environment variable before starting the server.  
To change the rosters password set the `ROSTER_PASSWORD` environment variable before starting the server.

### Troubleshooting

- **"Node.js is not installed"** – Run `install.bat` / `install.sh` first, or install Node.js manually from [https://nodejs.org](https://nodejs.org).
- **Port 3000 already in use** – The start script automatically stops any existing instance on that port. If it persists, restart your computer.
- **Frontend not loading** – Run the install script again; it will rebuild the frontend.

---

---

## Čeština

### Požadavky

- **Node.js v20 nebo novější** (npm je součástí Node.js – není třeba instalovat zvlášť)
- Windows 10/11, macOS 10.15+ nebo Linux
- Moderní webový prohlížeč (Chrome, Firefox, Edge, Safari)
- Během instalace je vyžadováno připojení k internetu, aby systém mohl stáhnout všechny potřebné moduly. Offline instalace nejsou podporovány.

### Stažení

- Stáhněte nejnovější vydání ze sekce „Releases" na GitHubu nebo naklonujte repozitář.
- Rozbalte ZIP do libovolné složky, ze které má být DD-MB spouštěno.

### Instalace

**Windows:**

1. Dvakrát klikněte na `install.bat`
2. Pokud Node.js není nainstalováno, skript se pokusí jej automaticky nainstalovat přes **winget** (součást Windows 10 1709+ a Windows 11). Pokud winget není k dispozici, postupujte podle pokynů na obrazovce a nainstalujte Node.js ručně z [https://nodejs.org](https://nodejs.org).
3. Po úspěšné instalaci skript vypíše **"Installation complete!"**

**macOS / Linux:**

1. Otevřete Terminal ve složce projektu
2. Spusťte:

   ```sh
   chmod +x install.sh
   ./install.sh
   ```

3. Na macOS skript nainstaluje Node.js přes **Homebrew** (pokud není nainstalováno). Pokud Homebrew chybí, postupujte podle pokynů na obrazovce.
4. Na Linuxu skript nainstaluje Node.js přes **NodeSource** (vyžaduje `curl` a `sudo`).
5. Po úspěšné instalaci skript vypíše **"Installation complete!"**

### Spuštění aplikace

**Windows:** Dvakrát klikněte na `start.bat`

**macOS / Linux:**

```sh
./start.sh
```

Poté otevřete prohlížeč na adrese: **http://localhost:3000**

### Výchozí přihlašovací údaje

| Role | Uživatelské jméno | Heslo |
| ---- | ----------------- | ----- |
| Admin | `admin` | `admin123` |
| Dispečer | název stanice (z rozevíracího menu) | název stanice malými písmeny bez diakritiky |
| Turnusy | `roster` | `rosters` |

Pro změnu hesla admina nastavte proměnnou prostředí `ADMIN_PASSWORD` před spuštěním serveru.  
Pro změnu hesla turnusů nastavte proměnnou prostředí `ROSTER_PASSWORD` před spuštěním serveru.

### Řešení problémů

- **"Node.js is not installed"** – Nejprve spusťte `install.bat` / `install.sh`, nebo nainstalujte Node.js ručně z [https://nodejs.org](https://nodejs.org).
- **Port 3000 je obsazen** – Startovací skript automaticky zastaví existující instanci na tomto portu. Pokud problém přetrvává, restartujte počítač.
- **Frontend se nenačítá** – Spusťte znovu instalační skript; ten znovu sestaví frontend.

---

---

## Slovenčina

### Požiadavky

- **Node.js v20 alebo novší** (npm je súčasťou Node.js – nie je potrebná samostatná inštalácia)
- Windows 10/11, macOS 10.15+ alebo Linux
- Moderný webový prehliadač (Chrome, Firefox, Edge, Safari)
- Počas inštalácie je potrebné pripojenie na internet, aby systém mohol stiahnuť všetky potrebné moduly. Offline inštalácie nie sú podporované.

### Stiahnutie

- Stiahnite najnovšie vydanie zo sekcie „Releases" na GitHube alebo naklonujte repozitár.
- Rozbaľte ZIP do ľubovoľného priečinka, z ktorého má byť DD-MB spúšťané.

### Inštalácia

**Windows:**

1. Dvakrát kliknite na `install.bat`
2. Ak Node.js nie je nainštalovaný, skript sa pokúsi ho automaticky nainštalovať cez **winget** (súčasť Windows 10 1709+ a Windows 11). Ak winget nie je k dispozícii, postupujte podľa pokynov na obrazovke a nainštalujte Node.js ručne z [https://nodejs.org](https://nodejs.org).
3. Po úspešnej inštalácii skript vypíše **"Installation complete!"**

**macOS / Linux:**

1. Otvorte Terminal v priečinku projektu
2. Spustite:

   ```sh
   chmod +x install.sh
   ./install.sh
   ```

3. Na macOS skript nainštaluje Node.js cez **Homebrew** (ak nie je nainštalovaný). Ak Homebrew chýba, postupujte podľa pokynov na obrazovke.
4. Na Linuxe skript nainštaluje Node.js cez **NodeSource** (vyžaduje `curl` a `sudo`).
5. Po úspešnej inštalácii skript vypíše **"Installation complete!"**

### Spustenie aplikácie

**Windows:** Dvakrát kliknite na `start.bat`

**macOS / Linux:**

```sh
./start.sh
```

Potom otvorte prehliadač na adrese: **http://localhost:3000**

### Predvolené prihlasovacie údaje

| Rola | Používateľské meno | Heslo |
| ---- | ------------------ | ----- |
| Admin | `admin` | `admin123` |
| Dispečer | názov stanice (z rozbaľovacieho menu) | názov stanice malými písmenami bez diakritiky |
| Turnusy | `roster` | `rosters` |

Na zmenu hesla admina nastavte premennú prostredia `ADMIN_PASSWORD` pred spustením servera.  
Na zmenu hesla turnusov nastavte premennú prostredia `ROSTER_PASSWORD` pred spustením servera.

### Riešenie problémov

- **"Node.js is not installed"** – Najprv spustite `install.bat` / `install.sh`, alebo nainštalujte Node.js ručne z [https://nodejs.org](https://nodejs.org).
- **Port 3000 je obsadený** – Štartovací skript automaticky zastaví existujúcu inštanciu na tomto porte. Ak problém pretrváva, reštartujte počítač.
- **Frontend sa nenačítava** – Spustite znovu inštalačný skript; ten znovu zostaví frontend.

---

---

## Polski

### Wymagania

- **Node.js v20 lub nowszy** (npm jest dołączony do Node.js – nie wymaga oddzielnej instalacji)
- Windows 10/11, macOS 10.15+ lub Linux
- Nowoczesna przeglądarka internetowa (Chrome, Firefox, Edge, Safari)
- Podczas instalacji wymagane jest połączenie z internetem, aby system mógł pobrać wszystkie niezbędne moduły. Instalacje offline nie są obsługiwane.

### Pobieranie

- Pobierz najnowsze wydanie z sekcji „Releases" na GitHubie lub sklonuj repozytorium.
- Wypakuj ZIP do dowolnego folderu, z którego ma być uruchamiane DD-MB.

### Instalacja

**Windows:**

1. Kliknij dwukrotnie `install.bat`
2. Jeżeli Node.js nie jest zainstalowany, skrypt spróbuje zainstalować go automatycznie przez **winget** (wbudowany w Windows 10 1709+ i Windows 11). Jeśli winget nie jest dostępny, postępuj zgodnie z instrukcjami na ekranie i zainstaluj Node.js ręcznie z [https://nodejs.org](https://nodejs.org).
3. Po pomyślnej instalacji skrypt wyświetli **"Installation complete!"**

**macOS / Linux:**

1. Otwórz Terminal w folderze projektu
2. Uruchom:

   ```sh
   chmod +x install.sh
   ./install.sh
   ```

3. Na macOS skrypt zainstaluje Node.js przez **Homebrew** (jeśli nie jest zainstalowany). Jeśli Homebrew nie jest dostępny, postępuj zgodnie z instrukcjami na ekranie.
4. Na Linuksie skrypt zainstaluje Node.js przez **NodeSource** (wymaga `curl` i `sudo`).
5. Po pomyślnej instalacji skrypt wyświetli **"Installation complete!"**

### Uruchamianie aplikacji

**Windows:** Kliknij dwukrotnie `start.bat`

**macOS / Linux:**

```sh
./start.sh
```

Następnie otwórz przeglądarkę pod adresem: **http://localhost:3000**

### Domyślne dane logowania

| Rola | Nazwa użytkownika | Hasło |
| ---- | ----------------- | ----- |
| Admin | `admin` | `admin123` |
| Dyspozytor | nazwa stacji (z listy rozwijanej) | nazwa stacji małymi literami bez znaków diakrytycznych |
| Turnusy | `roster` | `rosters` |

Aby zmienić hasło administratora, ustaw zmienną środowiskową `ADMIN_PASSWORD` przed uruchomieniem serwera.  
Aby zmienić hasło do turnusów, ustaw zmienną środowiskową `ROSTER_PASSWORD` przed uruchomieniem serwera.

### Rozwiązywanie problemów

- **"Node.js is not installed"** – Najpierw uruchom `install.bat` / `install.sh` lub zainstaluj Node.js ręcznie z [https://nodejs.org](https://nodejs.org).
- **Port 3000 jest zajęty** – Skrypt startowy automatycznie zatrzymuje istniejącą instancję na tym porcie. Jeśli problem nie ustępuje, uruchom ponownie komputer.
- **Frontend się nie ładuje** – Uruchom ponownie skrypt instalacyjny; przebuduje on frontend.

---

---

## Deutsch

### Voraussetzungen

- **Node.js v20 oder neuer** (npm ist in Node.js enthalten – keine separate Installation erforderlich)
- Windows 10/11, macOS 10.15+ oder Linux
- Ein moderner Webbrowser (Chrome, Firefox, Edge, Safari)
- Während der Installation ist eine Internetverbindung erforderlich, damit das System alle notwendigen Module herunterladen kann. Offline-Installationen werden nicht unterstützt.

### Download

- Laden Sie das neueste Release aus dem Bereich „Releases" auf GitHub herunter oder klonen Sie das Repository.
- Entpacken Sie die ZIP-Datei in einen beliebigen Ordner, von dem aus DD-MB gestartet werden soll.

### Installation

**Windows:**

1. Doppelklick auf `install.bat`
2. Falls Node.js nicht installiert ist, versucht das Skript, es automatisch über **winget** zu installieren (in Windows 10 1709+ und Windows 11 integriert). Wenn winget nicht verfügbar ist, folgen Sie den Anweisungen auf dem Bildschirm und installieren Sie Node.js manuell von [https://nodejs.org](https://nodejs.org).
3. Nach erfolgreicher Installation gibt das Skript **"Installation complete!"** aus.

**macOS / Linux:**

1. Öffnen Sie ein Terminal im Projektordner
2. Führen Sie aus:

   ```sh
   chmod +x install.sh
   ./install.sh
   ```

3. Auf macOS installiert das Skript Node.js über **Homebrew** (falls nicht installiert). Wenn Homebrew fehlt, folgen Sie den Anweisungen auf dem Bildschirm.
4. Auf Linux installiert das Skript Node.js über **NodeSource** (benötigt `curl` und `sudo`).
5. Nach erfolgreicher Installation gibt das Skript **"Installation complete!"** aus.

### Anwendung starten

**Windows:** Doppelklick auf `start.bat`

**macOS / Linux:**

```sh
./start.sh
```

Öffnen Sie anschließend Ihren Browser unter: **http://localhost:3000**

### Standard-Anmeldedaten

| Rolle | Benutzername | Passwort |
| ----- | ------------ | -------- |
| Admin | `admin` | `admin123` |
| Fahrdienstleiter | Stationsname (aus Dropdown) | Stationsname in Kleinbuchstaben ohne Sonderzeichen |
| Turnusse | `roster` | `rosters` |

Um das Admin-Passwort zu ändern, setzen Sie die Umgebungsvariable `ADMIN_PASSWORD` vor dem Serverstart.  
Um das Turnus-Passwort zu ändern, setzen Sie die Umgebungsvariable `ROSTER_PASSWORD` vor dem Serverstart.

### Problemlösung

- **"Node.js is not installed"** – Führen Sie zuerst `install.bat` / `install.sh` aus oder installieren Sie Node.js manuell von [https://nodejs.org](https://nodejs.org).
- **Port 3000 bereits belegt** – Das Startskript stoppt automatisch eine vorhandene Instanz auf diesem Port. Falls das Problem bestehen bleibt, starten Sie den Computer neu.
- **Frontend wird nicht geladen** – Führen Sie das Installationsskript erneut aus; es erstellt das Frontend neu.

---

---

## Magyar

### Követelmények

- **Node.js v20 vagy újabb** (az npm bele van építve a Node.js csomagba – nincs szükség különálló telepítésre)
- Windows 10/11, macOS 10.15+ vagy Linux
- Modern webböngésző (Chrome, Firefox, Edge, Safari)
- A telepítés során internetkapcsolat szükséges, hogy a rendszer le tudja tölteni az összes szükséges modult. Offline telepítés nem támogatott.

### Letöltés

- Töltse le a legújabb kiadást a GitHub „Releases" részéből, vagy klónozza a repozitóriumot.
- Csomagolja ki a ZIP fájlt bármely mappába, ahonnan a DD-MB-t indítani szeretné.

### Telepítés

**Windows:**

1. Dupla kattintás az `install.bat` fájlra
2. Ha a Node.js nincs telepítve, a szkript megpróbálja automatikusan telepíteni a **winget** segítségével (beépítve Windows 10 1709+ és Windows 11 rendszerekbe). Ha a winget nem érhető el, kövesse a képernyőn megjelenő utasításokat, és telepítse a Node.js-t kézzel a [https://nodejs.org](https://nodejs.org) oldalról.
3. Sikeres telepítés után a szkript kiírja: **"Installation complete!"**

**macOS / Linux:**

1. Nyisson meg egy Terminalt a projekt mappájában
2. Futtassa:

   ```sh
   chmod +x install.sh
   ./install.sh
   ```

3. macOS rendszeren a szkript a **Homebrew** segítségével telepíti a Node.js-t (ha nincs telepítve). Ha a Homebrew hiányzik, kövesse a képernyőn megjelenő utasításokat.
4. Linux rendszeren a szkript a **NodeSource** segítségével telepíti a Node.js-t (szükséges: `curl` és `sudo`).
5. Sikeres telepítés után a szkript kiírja: **"Installation complete!"**

### Az alkalmazás indítása

**Windows:** Dupla kattintás a `start.bat` fájlra

**macOS / Linux:**

```sh
./start.sh
```

Ezután nyissa meg a böngészőt a következő címen: **http://localhost:3000**

### Alapértelmezett bejelentkezési adatok

| Szerepkör | Felhasználónév | Jelszó |
| --------- | -------------- | ------ |
| Admin | `admin` | `admin123` |
| Forgalmi | állomás neve (legördülő menüből) | az állomás neve kis betűvel, érsékesítőjel nélkül |
| Turnusok | `roster` | `rosters` |

Az admin jelszavának megváltoztatásához állítsa be az `ADMIN_PASSWORD` környezeti változót a szerver indítása előtt.  
A turnusok jelszavának megváltoztatásához állítsa be a `ROSTER_PASSWORD` környezeti változót a szerver indítása előtt.

### Hibaelhárítás

- **"Node.js is not installed"** – Először futtassa az `install.bat` / `install.sh` fájlt, vagy telepítse a Node.js-t kézzel a [https://nodejs.org](https://nodejs.org) oldalról.
- **A 3000-es port már foglalt** – Az indítószkript automatikusan leállítja az adott porton lévő meglévő példányt. Ha a probléma megmarad, indítsa újra a számítógépet.
- **A frontend nem töltődik be** – Futtassa újra a telepítőszkriptet; az újraépíti a frontendet.

---
