# DD-MB – Initial Setup Guide

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

- [Grafikon](https://github.com/jub77/grafikon) application by jub77.
- GTM file for the meeting.

---

### Pre-Check

Before generating any exports from Grafikon, verify the following:

- [ ] All stations with human dispatchers must be of type **Branch Station**, **Station**, or **Technical Station**. If a station with a dispatcher is currently of type **Split**, change its type to **Station**.
- [ ] To simplify import and automatic block recognition, review all station abbreviations in Grafikon (Net view). The easiest convention is to use the first three letters of the station name.

---

### Step 1 — Upload Alert Sounds

By default, six alert sounds are bundled with DD-MB. If you need additional sounds, upload them via the admin portal in the **Sound Library** section. You can also change the global default alert sound from the same section.

---

### Step 2 — Import Layout

Export station data as CSV files from Grafikon:

1. In Grafikon go to **Outputs → Outputs…**
2. Select **"text: Station timetables (CSV) [embedded]"**
3. Click **Generate output**.

> [!IMPORTANT]
> If you need station names or notes in a specific language for an international meeting, change the output language in Grafikon before generating. DD-MB uses the exported text as-is and does not translate it.

Once you have all CSV exports in one folder, pack them into a single ZIP file.

Log in to the DD-MB admin portal. Under **Import ZIP**, select the ZIP file and click **Upload**. A success or error message will appear below the file picker.

---

### Step 3 — Validate and Configure Stations

1. In the admin portal, open the **Station configuration** section.
2. Expand each station and confirm there is no yellow **⚠ unresolved** warning next to any station abbreviation. If warnings appear, correct the block mappings.
3. For each station, assign neighbours to the **Left** and **Right** dispatcher sides. If the station uses a multi-track block, adjust the number of block slots accordingly.
4. Fill in the **phone number** shortcut if your event uses phone coordination.
5. Optionally, select a **default alert sound** for each individual station. Dispatchers can also change their own alert sound from within the dispatcher view.
6. If the station is a **hidden station** without a human dispatcher (staging loops, fiddle yards, etc.), configure the appropriate hidden station type — see [Hidden Station Types](#hidden-station-types) below.
7. Review the **Tracks** field for each station. It is pre-populated from the CSV import based on platform values in the timetable. Add any tracks used at the event that were not present in the Grafikon data.

---

### Step 4 (Optional) — Graphical Timetables

To bundle graphical timetables inside DD-MB, generate them in Grafikon and upload the SVG files in the **Graphical timetables** section of the admin portal.

> [!TIP]
> Always tune the output dimensions in Grafikon to make timetables readable — DD-MB displays SVGs at their native size without resizing. To adjust: **Outputs → Outputs… → select "svg: Graphical timetables [embedded]" → click the properties icon → set Width, Height, Zoom, and Max height**. Several iterations are usually needed to get a clean result.

---

### Step 5 (Optional) — Circulations / Rosters

To track crew rosters inside DD-MB, export all circulations from Grafikon (**svg: Graphical output of circulations [embedded]**) and import the file in the **Circulations** section of the admin portal.

---

### Step 6 (Optional) — Export Initial Configuration

It is good practice to export the full station configuration (block assignments, sounds, phone numbers, etc.) immediately after setup, so it can be restored quickly after a total failure or reset. Use the **Export / import configuration** section in the admin portal to create and download a backup. After any future reset of DD-MB, re-importing this file skips most of Step 3.

---

### Step 7 (Optional) — Passwords

Custom passwords can be set for the admin portal, Rosters, and individual dispatcher stations:

- **Admin portal** and **Rosters** passwords are configured at the bottom of the admin portal in the **Passwords** section.
- **Dispatcher** passwords are set per station inside the individual station details in the **Station configuration** section.

If no custom password is set, each role falls back to its default: the admin portal uses the `ADMIN_PASSWORD` environment variable (default: `admin123`), Rosters uses `ROSTER_PASSWORD` (default: `rosters`), and dispatcher stations use the normalised station name as the password.

---

### Hidden Station Types

Two special modes are available for stations that are not operated by a human dispatcher.

#### Automatic

An automatic hidden station operates without any manual interaction:

- When a neighbouring dispatcher sends a train to this station, the offer is **accepted automatically**.
- Once the sending dispatcher marks the train as departed, the arriving train is marked as **complete** after a configurable timeout and removed from the layout permanently.
- When a neighbouring station expects a train **from** an automatic hidden station, that train must be added to the layout manually by the neighbouring dispatcher. It will appear as if dispatched from the hidden station and will occupy the block accordingly.

> [!IMPORTANT]
> Automatic hidden stations do **not** assign trains to blocks automatically.

#### Simplified

A simplified hidden station is a lightweight frontend intended for train drivers to operate themselves — no dispatcher knowledge required. It shows the next 6 upcoming trains and:

- **Automatically offers** the train to the adjacent station.
- **Automatically accepts** offers arriving from the adjacent station.
- Allows drivers to confirm arrival and remove the train from the layout with a single tap.

The main purpose is to let train drivers manage their own movements at staging areas without needing operational knowledge of DD-MB.

---

## Čeština

### Požadavky

- Aplikace [Grafikon](https://github.com/jub77/grafikon) od jub77.
- GTM soubor pro setkání.

---

### Předběžná kontrola

Před generováním jakýchkoliv exportů z Grafikonu ověřte následující:

- [ ] Všechny stanice s lidskými výpravčími musí být typu **Odbočka**, **Stanice** nebo **Technická stanice**. Pokud má stanice s výpravčím typ **Větvení**, změňte jej na **Stanice**.
- [ ] Pro zjednodušení importu a automatického rozpoznávání bloků zkontrolujte všechny zkratky stanic v Grafikonu (zobrazení Síť). Nejjednodušší konvencí je použití prvních tří písmen názvu stanice.

---

### Krok 1 — Nahrání zvukových upozornění

Ve výchozím stavu je v DD-MB zahrnuto šest zvukových upozornění. Pokud potřebujete další zvuky, nahrajte je přes administrátorský portál v sekci **Zvuková knihovna**. Zde můžete také změnit výchozí zvuk upozornění pro celý systém.

---

### Krok 2 — Import rozvržení

Exportujte data stanic jako CSV soubory z Grafikonu:

1. V Grafikonu přejděte na **Výstupy → Výstupy…**
2. Vyberte **„text: Staničenkové jízdní řády (CSV) [embedded]"**
3. Klikněte na **Generovat výstup**.

> [!IMPORTANT]
> Pokud potřebujete názvy stanic nebo poznámky v konkrétním jazyce pro mezinárodní setkání, změňte jazyk výstupu v Grafikonu před generováním. DD-MB používá exportovaný text tak, jak je, a neprovádí žádný překlad.

Jakmile máte všechny CSV exporty v jedné složce, zabalte je do jednoho ZIP souboru.

Přihlaste se do administrátorského portálu DD-MB. V části **Import ZIP** vyberte ZIP soubor a klikněte na **Nahrát**. Pod výběrem souboru se zobrazí zpráva o úspěchu nebo chybě.

---

### Krok 3 — Ověření a konfigurace stanic

1. V administrátorském portálu otevřete sekci **Konfigurace stanic**.
2. Rozbalte každou stanici a zkontrolujte, zda se u žádné zkratky stanice nezobrazuje žluté varování **⚠ unresolved**. Pokud varování existuje, opravte mapování bloků.
3. Pro každou stanici přiřaďte sousedy na strany **Vlevo** a **Vpravo** od výpravčího. Pokud stanice používá vícekolejný blok, odpovídajícím způsobem upravte počet slotů bloku.
4. Vyplňte zkratku **telefonního čísla**, pokud vaše setkání využívá telefonní koordinaci.
5. Volitelně vyberte **výchozí zvuk upozornění** pro každou jednotlivou stanici. Výpravčí si mohou svůj zvuk upozornění změnit také přímo z výpravčího zobrazení.
6. Pokud je stanice **skrytou stanicí** bez lidského výpravčího (odstavné smyčky, přesuvny apod.), nakonfigurujte odpovídající typ skryté stanice — viz [Typy skrytých stanic](#typy-skrytých-stanic) níže.
7. Zkontrolujte pole **Koleje** pro každou stanici. Je předvyplněno z CSV importu na základě hodnot nástupišť v jízdním řádu. Přidejte koleje používané na setkání, které nejsou obsaženy v datech Grafikonu.

---

### Krok 4 (Volitelný) — Grafické jízdní řády

Chcete-li zahrnout grafické jízdní řády do DD-MB, vygenerujte je v Grafikonu a nahrajte SVG soubory v sekci **Grafické jízdní řády** administrátorského portálu.

> [!TIP]
> Vždy upravte výstupní rozměry v Grafikonu tak, aby byly jízdní řády čitelné — DD-MB zobrazuje SVG soubory v jejich nativní velikosti bez změny. Postup: **Výstupy → Výstupy… → vyberte „svg: Grafické jízdní řády [embedded]" → klikněte na ikonu vlastností → nastavte Šířku, Výšku, Zoom a Max výšku**. K dosažení čistého výsledku je obvykle potřeba několik pokusů.

---

### Krok 5 (Volitelný) — Oběhy / Turnusy

Chcete-li sledovat posádky v DD-MB, exportujte všechny oběhy z Grafikonu (**svg: Grafický výstup oběhů [embedded]**) a importujte soubor v sekci **Turnusy** administrátorského portálu.

---

### Krok 6 (Volitelný) — Export počáteční konfigurace

Je dobrým zvykem exportovat celou konfiguraci stanic (přiřazení bloků, zvuky, telefonní čísla atd.) ihned po nastavení, aby bylo možné ji rychle obnovit po úplném selhání nebo resetování. Použijte sekci **Export / import konfigurace** v administrátorském portálu k vytvoření a stažení zálohy. Po jakémkoliv budoucím resetu DD-MB obnoví reimport tohoto souboru většinu kroků 3.

---

### Krok 7 (Volitelný) — Hesla

Vlastní hesla lze nastavit pro administrátorský portál, Turnusy a jednotlivé stanice výpravčích:

- Hesla pro **administrátorský portál** a **Turnusy** se nastavují ve spodní části administrátorského portálu v sekci **Hesla**.
- Heslo **výpravčího** se nastavuje pro každou stanici zvlášť v detailu stanice v sekci **Konfigurace stanic**.

Pokud není vlastní heslo nastaveno, každá role používá výchozí hodnotu: administrátorský portál používá proměnnou prostředí `ADMIN_PASSWORD` (výchozí: `admin123`), Turnusy používají `ROSTER_PASSWORD` (výchozí: `rosters`) a stanice výpravčích používají normalizovaný název stanice jako heslo.

---

### Typy skrytých stanic

Pro stanice, které nejsou obsluhovány lidským výpravčím, jsou k dispozici dva speciální režimy.

#### Automatická

Automatická skrytá stanice funguje bez jakékoliv manuální interakce:

- Když sousední výpravčí odešle vlak do této stanice, nabídka je **přijata automaticky**.
- Jakmile odesílající výpravčí označí vlak jako odjezd, příjezd vlaku je po nastavitelném timeoutu označen jako **dokončený** a vlak je trvale odstraněn z layoutu.
- Pokud sousední stanice očekává vlak **od** automatické skryté stanice, musí tento vlak do rozvržení přidat ručně sousední výpravčí. Zobrazí se jako vypravený ze skryté stanice a obsadí odpovídající blok.

> [!IMPORTANT]
> Automatické skryté stanice **nepřiřazují** vlaky do bloků automaticky.

#### Zjednodušená

Zjednodušená skrytá stanice je odlehčené rozhraní určené pro obsluhu samotnými strojvedoucími — bez potřeby znalosti práce výpravčího. Zobrazuje následujících 6 vlaků a:

- **Automaticky nabízí** vlak sousední stanici.
- **Automaticky přijímá** nabídky přicházející od sousední stanice.
- Umožňuje strojvedoucím potvrdit příjezd a odstranit vlak z rozvržení jedním klepnutím.

Hlavním účelem je umožnit strojvedoucím řídit vlastní pohyby v odstavných oblastech bez hluboké znalosti DD-MB.

---

## Slovenčina

### Požiadavky

- Aplikácia [Grafikon](https://github.com/jub77/grafikon) od jub77.
- GTM súbor pre stretnutie.

---

### Predbežná kontrola

Pred generovaním akýchkoľvek exportov z Grafikonu overte nasledujúce:

- [ ] Všetky stanice s ľudskými výpravcami musia byť typu **Odbočka**, **Stanica** alebo **Technická stanica**. Ak má stanica s výpravcom typ **Vetvenie**, zmeňte ho na **Stanica**.
- [ ] Pre zjednodušenie importu a automatického rozpoznávania blokov skontrolujte všetky skratky staníc v Grafikone (zobrazenie Sieť). Najjednoduchšou konvenciou je použitie prvých troch písmen názvu stanice.

---

### Krok 1 — Nahranie zvukových upozornení

V predvolenom stave je v DD-MB zahrnutých šesť zvukových upozornení. Ak potrebujete ďalšie zvuky, nahrajte ich cez administrátorský portál v sekcii **Zvuková knižnica**. Tu môžete tiež zmeniť predvolený zvuk upozornenia pre celý systém.

---

### Krok 2 — Import rozloženia

Exportujte údaje staníc ako CSV súbory z Grafikonu:

1. V Grafikone prejdite na **Výstupy → Výstupy…**
2. Vyberte **„text: Staničenkové cestovné poriadky (CSV) [embedded]"**
3. Kliknite na **Generovať výstup**.

> [!IMPORTANT]
> Ak potrebujete názvy staníc alebo poznámky v konkrétnom jazyku pre medzinárodné stretnutie, zmeňte jazyk výstupu v Grafikone pred generovaním. DD-MB používa exportovaný text tak, ako je, a nevykonáva žiadny preklad.

Keď máte všetky CSV exporty v jednom priečinku, zabaľte ich do jedného ZIP súboru.

Prihláste sa do administrátorského portálu DD-MB. V časti **Import ZIP** vyberte ZIP súbor a kliknite na **Nahrať**. Pod výberom súboru sa zobrazí správa o úspechu alebo chybe.

---

### Krok 3 — Overenie a konfigurácia staníc

1. V administrátorskom portáli otvorte sekciu **Konfigurácia staníc**.
2. Rozbaľte každú stanicu a skontrolujte, či sa pri žiadnej skratke stanice nezobrazuje žlté varovanie **⚠ unresolved**. Ak varovanie existuje, opravte mapovanie blokov.
3. Pre každú stanicu priraďte susedov na strany **Vľavo** a **Vpravo** od výpravcu. Ak stanica používa viackoľajový blok, zodpovedajúcim spôsobom upravte počet slotov bloku.
4. Vyplňte skratku **telefónneho čísla**, ak vaše stretnutie využíva telefónnu koordináciu.
5. Voliteľne vyberte **predvolený zvuk upozornenia** pre každú jednotlivú stanicu. Výpravcovia si môžu svoj zvuk upozornenia zmeniť aj priamo zo zobrazenia výpravcu.
6. Ak je stanica **skrytou stanicou** bez ľudského výpravcu (odstavné slučky, presuny a pod.), nakonfigurujte zodpovedajúci typ skrytej stanice — pozri [Typy skrytých staníc](#typy-skrytých-staníc) nižšie.
7. Skontrolujte pole **Koľaje** pre každú stanicu. Je predvyplnené z CSV importu na základe hodnôt nástupíšť v cestovnom poriadku. Pridajte koľaje používané na stretnutí, ktoré nie sú obsiahnuté v údajoch Grafikonu.

---

### Krok 4 (Voliteľný) — Grafické cestovné poriadky

Ak chcete zahrnúť grafické cestovné poriadky do DD-MB, vygenerujte ich v Grafikone a nahrajte SVG súbory v sekcii **Grafické cestovné poriadky** administrátorského portálu.

> [!TIP]
> Vždy upravte výstupné rozmery v Grafikone tak, aby boli cestovné poriadky čitateľné — DD-MB zobrazuje SVG súbory v ich natívnej veľkosti bez zmeny. Postup: **Výstupy → Výstupy… → vyberte „svg: Grafické cestovné poriadky [embedded]" → kliknite na ikonu vlastností → nastavte Šírku, Výšku, Zoom a Max výšku**. Na dosiahnutie čistého výsledku je zvyčajne potrebných niekoľko pokusov.

---

### Krok 5 (Voliteľný) — Obehy / Turnusy

Ak chcete sledovať posádky v DD-MB, exportujte všetky obehy z Grafikonu (**svg: Grafický výstup obehov [embedded]**) a importujte súbor v sekcii **Turnusy** administrátorského portálu.

---

### Krok 6 (Voliteľný) — Export počiatočnej konfigurácie

Je dobrou praxou exportovať celú konfiguráciu staníc (priradenie blokov, zvuky, telefónne čísla atď.) ihneď po nastavení, aby bolo možné ju rýchlo obnoviť po úplnom zlyhaní alebo resetovaní. Použite sekciu **Export / import konfigurácie** v administrátorskom portáli na vytvorenie a stiahnutie zálohy. Po akomkoľvek budúcom resete DD-MB obnoví reimport tohto súboru väčšinu krokov 3.

---

### Krok 7 (Voliteľný) — Heslá

Vlastné heslá je možné nastaviť pre administrátorský portál, Turnusy a jednotlivé stanice výpravcov:

- Heslá pre **administrátorský portál** a **Turnusy** sa nastavujú v spodnej časti administrátorského portálu v sekcii **Heslá**.
- Heslo **výpravcu** sa nastavuje pre každú stanicu zvlášť v detaile stanice v sekcii **Konfigurácia staníc**.

Ak nie je vlastné heslo nastavené, každá rola používa predvolenú hodnotu: administrátorský portál používa premennú prostredia `ADMIN_PASSWORD` (predvolené: `admin123`), Turnusy používajú `ROSTER_PASSWORD` (predvolené: `rosters`) a stanice výpravcov používajú normalizovaný názov stanice ako heslo.

---

### Typy skrytých staníc

Pre stanice, ktoré nie sú obsluhované ľudským výpravcom, sú k dispozícii dva špeciálne režimy.

#### Automatická

Automatická skrytá stanica funguje bez akejkoľvek manuálnej interakcie:

- Keď susedný výpravca odošle vlak do tejto stanice, ponuka je **prijatá automaticky**.
- Akonáhle odosielajúci výpravca označí vlak ako odchod, príjazd vlaku je po nastaviteľnom časovom limite označený ako **dokončený** a vlak je trvalo odstránený z layoutu.
- Ak susedná stanica očakáva vlak **od** automatickej skrytej stanice, musí tento vlak do rozloženia pridať ručne susedný výpravca. Zobrazí sa ako vypravený zo skrytej stanice a obsadí zodpovedajúci blok.

> [!IMPORTANT]
> Automatické skryté stanice **nepriradávajú** vlaky do blokov automaticky.

#### Zjednodušená

Zjednodušená skrytá stanica je odľahčené rozhranie určené na obsluhu samotnými strojvodcami — bez potreby znalosti práce výpravcu. Zobrazuje nasledujúcich 6 vlakov a:

- **Automaticky ponúka** vlak susednej stanici.
- **Automaticky prijíma** ponuky prichádzajúce od susednej stanice.
- Umožňuje strojvodcom potvrdiť príjazd a odstrániť vlak z rozloženia jedným klepnutím.

Hlavným účelom je umožniť strojvodcom riadiť vlastné pohyby v odstavných oblastiach bez hlbokej znalosti DD-MB.

---

## Polski

### Wymagania

- Aplikacja [Grafikon](https://github.com/jub77/grafikon) autorstwa jub77.
- Plik GTM dla spotkania.

---

### Wstępna kontrola

Przed wygenerowaniem jakichkolwiek eksportów z Grafikonu sprawdź poniższe:

- [ ] Wszystkie stacje z ludzkimi dyżurnymi muszą być typu **Stacja odgałęźna**, **Stacja** lub **Stacja techniczna**. Jeśli stacja z dyżurnym ma typ **Rozgałęzienie**, zmień go na **Stacja**.
- [ ] Aby uprościć import i automatyczne rozpoznawanie bloków, przejrzyj skróty wszystkich stacji w Grafikonie (widok Sieć). Najprostszą konwencją jest użycie pierwszych trzech liter nazwy stacji.

---

### Krok 1 — Wgrywanie dźwięków alertów

Domyślnie DD-MB zawiera sześć dźwięków alertów. Jeśli potrzebujesz dodatkowych dźwięków, wgraj je przez portal administratora w sekcji **Biblioteka dźwięków**. Możesz tam również zmienić globalny domyślny dźwięk alertu.

---

### Krok 2 — Import układu

Wyeksportuj dane stacji jako pliki CSV z Grafikonu:

1. W Grafikonie przejdź do **Wyjścia → Wyjścia…**
2. Wybierz **„text: Rozkłady jazdy stacji (CSV) [embedded]"**
3. Kliknij **Generuj wyjście**.

> [!IMPORTANT]
> Jeśli potrzebujesz nazw stacji lub notatek w określonym języku na spotkanie międzynarodowe, zmień język wyjścia w Grafikonie przed generowaniem. DD-MB używa eksportowanego tekstu bez zmian i nie wykonuje żadnych tłumaczeń.

Gdy wszystkie pliki CSV znajdą się w jednym folderze, spakuj je do jednego pliku ZIP.

Zaloguj się do portalu administratora DD-MB. W sekcji **Import ZIP** wybierz plik ZIP i kliknij **Wgraj**. Poniżej selektora pliku pojawi się komunikat o powodzeniu lub błędzie.

---

### Krok 3 — Weryfikacja i konfiguracja stacji

1. W portalu administratora otwórz sekcję **Konfiguracja stacji**.
2. Rozwiń każdą stację i upewnij się, że przy żadnym skrócie stacji nie widać żółtego ostrzeżenia **⚠ unresolved**. Jeśli ostrzeżenie istnieje, popraw mapowanie bloków.
3. Dla każdej stacji przypisz sąsiadów do stron **Lewo** i **Prawo** od dyżurnego. Jeśli stacja używa wielotorowego bloku, odpowiednio dostosuj liczbę slotów bloku.
4. Wypełnij skrót **numeru telefonu**, jeśli Twoje spotkanie korzysta z koordynacji telefonicznej.
5. Opcjonalnie wybierz **domyślny dźwięk alertu** dla każdej poszczególnej stacji. Dyżurni mogą również zmienić swój dźwięk alertu bezpośrednio z widoku dyżurnego.
6. Jeśli stacja jest **stacją ukrytą** bez ludzkiego dyżurnego (pętle postojowe, przesuwnice itp.), skonfiguruj odpowiedni typ stacji ukrytej — patrz [Typy stacji ukrytych](#typy-stacji-ukrytych) poniżej.
7. Sprawdź pole **Tory** dla każdej stacji. Jest wstępnie wypełnione na podstawie importu CSV z wartości peronów w rozkładzie jazdy. Dodaj tory używane na spotkaniu, których nie ma w danych Grafikonu.

---

### Krok 4 (Opcjonalny) — Graficzne rozkłady jazdy

Aby dołączyć graficzne rozkłady jazdy do DD-MB, wygeneruj je w Grafikonie i wgraj pliki SVG w sekcji **Graficzne rozkłady jazdy** portalu administratora.

> [!TIP]
> Zawsze dostosuj wymiary wyjściowe w Grafikonie, aby rozkłady jazdy były czytelne — DD-MB wyświetla pliki SVG w ich natywnym rozmiarze bez skalowania. Sposób: **Wyjścia → Wyjścia… → wybierz „svg: Graficzne rozkłady jazdy [embedded]" → kliknij ikonę właściwości → ustaw Szerokość, Wysokość, Zoom i Maks. wysokość**. Uzyskanie czystego rezultatu wymaga zazwyczaj kilku prób.

---

### Krok 5 (Opcjonalny) — Obiegi / Turnusy

Aby śledzić obsady w DD-MB, wyeksportuj wszystkie obiegi z Grafikonu (**svg: Graficzny wydruk obiegów [embedded]**) i zaimportuj plik w sekcji **Turnusy** portalu administratora.

---

### Krok 6 (Opcjonalny) — Eksport konfiguracji początkowej

Dobrą praktyką jest wyeksportowanie pełnej konfiguracji stacji (przypisania bloków, dźwięki, numery telefonów itp.) natychmiast po konfiguracji, aby można ją było szybko przywrócić po awarii lub resetowaniu. Skorzystaj z sekcji **Eksport / import konfiguracji** w portalu administratora, aby utworzyć i pobrać kopię zapasową. Po każdym przyszłym resecie DD-MB ponowny import tego pliku pomija większość Kroku 3.

---

### Krok 7 (Opcjonalny) — Hasła

Niestandardowe hasła można ustawić dla portalu administratora, Turnusów i poszczególnych stacji dyżurnych:

- Hasła dla **portalu administratora** i **Turnusów** są konfigurowane w dolnej części portalu administratora w sekcji **Hasła**.
- Hasło **dyżurnego** jest ustawiane osobno dla każdej stacji w szczegółach stacji w sekcji **Konfiguracja stacji**.

Jeśli niestandardowe hasło nie jest ustawione, każda rola używa wartości domyślnej: portal administratora używa zmiennej środowiskowej `ADMIN_PASSWORD` (domyślne: `admin123`), Turnusy używają `ROSTER_PASSWORD` (domyślne: `rosters`), a stacje dyżurnych używają znormalizowanej nazwy stacji jako hasła.

---

### Typy stacji ukrytych

Dla stacji nieobsługiwanych przez ludzkiego dyżurnego dostępne są dwa specjalne tryby.

#### Automatyczna

Automatyczna stacja ukryta działa bez żadnej ręcznej interakcji:

- Gdy sąsiedni dyżurny wysyła pociąg do tej stacji, oferta jest **akceptowana automatycznie**.
- Gdy wysyłający dyżurny oznaczy pociąg jako odjazd, przybycie pociągu jest po konfigurowalnym czasie oznaczane jako **zakończone** i pociąg jest trwale usuwany z layoutu.
- Gdy sąsiednia stacja oczekuje pociągu **od** automatycznej stacji ukrytej, pociąg ten musi zostać ręcznie dodany do układu przez sąsiedniego dyżurnego. Pojawi się jako wysłany ze stacji ukrytej i zajmie odpowiedni blok.

> [!IMPORTANT]
> Automatyczne stacje ukryte **nie przypisują** pociągów do bloków automatycznie.

#### Uproszczona

Uproszczona stacja ukryta to uproszczony interfejs przeznaczony do obsługi przez samych maszynistów — bez potrzeby znajomości obsługi dyżurnego. Wyświetla następnych 6 pociągów i:

- **Automatycznie oferuje** pociąg sąsiedniej stacji.
- **Automatycznie akceptuje** oferty przychodzące od sąsiedniej stacji.
- Pozwala maszynistom potwierdzić przyjazd i usunąć pociąg z układu jednym dotknięciem.

Głównym celem jest umożliwienie maszynistom zarządzania własnymi ruchami na terenach postojowych bez głębokiej znajomości DD-MB.

---

## Deutsch

### Voraussetzungen

- Anwendung [Grafikon](https://github.com/jub77/grafikon) von jub77.
- GTM-Datei für das Treffen.

---

### Vorabprüfung

Vor der Erstellung von Exporten aus Grafikon folgendes überprüfen:

- [ ] Alle Bahnhöfe mit menschlichen Fahrdienstleitern müssen vom Typ **Abzweigbahnhof**, **Bahnhof** oder **Technischer Bahnhof** sein. Wenn ein Bahnhof mit Fahrdienstleiter vom Typ **Verzweigung** ist, diesen auf **Bahnhof** ändern.
- [ ] Um Import und automatische Blockerkennung zu vereinfachen, alle Bahnhofsabkürzungen in Grafikon (Netz-Ansicht) überprüfen. Die einfachste Konvention ist die Verwendung der ersten drei Buchstaben des Bahnhofsnamens.

---

### Schritt 1 — Alarmtöne hochladen

Standardmäßig enthält DD-MB sechs Alarmtöne. Falls weitere benötigt werden, können diese über das Admin-Portal im Bereich **Tonbibliothek** hochgeladen werden. Dort kann auch der globale Standard-Alarmton geändert werden.

---

### Schritt 2 — Layout importieren

Bahnhofsdaten als CSV-Dateien aus Grafikon exportieren:

1. In Grafikon zu **Ausgaben → Ausgaben…** navigieren.
2. **„text: Bahnhofs-Fahrpläne (CSV) [embedded]"** auswählen.
3. **Ausgabe generieren** klicken.

> [!IMPORTANT]
> Wenn für ein internationales Treffen Bahnhofsnamen oder Hinweise in einer bestimmten Sprache benötigt werden, die Ausgabesprache in Grafikon vor der Generierung ändern. DD-MB übernimmt den exportierten Text unverändert und führt keine Übersetzungen durch.

Sobald alle CSV-Exporte in einem Ordner vorliegen, diese in eine einzige ZIP-Datei packen.

Im Admin-Portal von DD-MB anmelden. Unter **Import ZIP** die ZIP-Datei auswählen und **Hochladen** klicken. Unterhalb der Dateiauswahl erscheint eine Erfolgs- oder Fehlermeldung.

---

### Schritt 3 — Bahnhöfe überprüfen und konfigurieren

1. Im Admin-Portal den Bereich **Bahnhofskonfiguration** öffnen.
2. Jeden Bahnhof aufklappen und sicherstellen, dass bei keiner Bahnhofsabkürzung die gelbe Warnung **⚠ unresolved** erscheint. Falls vorhanden, die Blockmappings korrigieren.
3. Für jeden Bahnhof Nachbarn den Seiten **Links** und **Rechts** des Fahrdienstleiters zuweisen. Bei Mehrgleisblöcken die Anzahl der Blockslots entsprechend anpassen.
4. Die **Telefon**-Abkürzung ausfüllen, wenn das Treffen telefonische Koordination nutzt.
5. Optional einen **Standard-Alarmton** für jeden einzelnen Bahnhof festlegen. Fahrdienstleiter können ihren Alarmton auch direkt aus der Dispatcher-Ansicht ändern.
6. Wenn der Bahnhof ein **versteckter Bahnhof** ohne menschlichen Fahrdienstleiter ist (Abstellschleifen, Abstellbahnhöfe usw.), den entsprechenden Typ des versteckten Bahnhofs konfigurieren — siehe [Typen versteckter Bahnhöfe](#typen-versteckter-bahnhöfe) unten.
7. Das Feld **Gleise** für jeden Bahnhof überprüfen. Es wird beim CSV-Import automatisch aus den Bahnsteigwerten des Fahrplans befüllt. Gleise hinzufügen, die beim Treffen genutzt werden, aber nicht in den Grafikon-Daten vorhanden sind.

---

### Schritt 4 (Optional) — Grafische Fahrpläne

Um grafische Fahrpläne in DD-MB einzubinden, diese in Grafikon generieren und die SVG-Dateien im Bereich **Grafische Fahrpläne** des Admin-Portals hochladen.

> [!TIP]
> Die Ausgabemaße in Grafikon immer so anpassen, dass die Fahrpläne lesbar sind — DD-MB zeigt SVG-Dateien in ihrer nativen Größe ohne Skalierung an. Vorgehen: **Ausgaben → Ausgaben… → „svg: Grafische Fahrpläne [embedded]" auswählen → Eigenschaften-Symbol klicken → Breite, Höhe, Zoom und Max. Höhe einstellen**. Für ein sauberes Ergebnis sind in der Regel mehrere Versuche nötig.

---

### Schritt 5 (Optional) — Umläufe / Turnusse

Um Personalumläufe in DD-MB zu verfolgen, alle Umläufe aus Grafikon exportieren (**svg: Grafische Ausgabe der Umläufe [embedded]**) und die Datei im Bereich **Turnusse** des Admin-Portals importieren.

---

### Schritt 6 (Optional) — Erstkonfiguration exportieren

Es empfiehlt sich, die vollständige Bahnhofskonfiguration (Blockzuweisungen, Töne, Telefonnummern usw.) unmittelbar nach der Einrichtung zu exportieren, damit diese nach einem Totalausfall oder Reset schnell wiederhergestellt werden kann. Den Bereich **Export / Import Konfiguration** im Admin-Portal verwenden, um eine Sicherungskopie zu erstellen und herunterzuladen. Nach einem künftigen Reset von DD-MB überspringt der Reimport dieser Datei den größten Teil von Schritt 3.

---

### Schritt 7 (Optional) — Passwörter

Benutzerdefinierte Passwörter können für das Admin-Portal, Turnusse und einzelne Fahrdienstleiter-Bahnhöfe festgelegt werden:

- Die Passwörter für **Admin-Portal** und **Turnusse** werden im unteren Bereich des Admin-Portals im Abschnitt **Passwörter** konfiguriert.
- Das **Fahrdienstleiter**-Passwort wird pro Bahnhof in den Bahnhofsdetails im Abschnitt **Bahnhofskonfiguration** festgelegt.

Ist kein benutzerdefiniertes Passwort gesetzt, verwendet jede Rolle ihren Standardwert: Das Admin-Portal nutzt die Umgebungsvariable `ADMIN_PASSWORD` (Standard: `admin123`), Turnusse nutzen `ROSTER_PASSWORD` (Standard: `rosters`), und Fahrdienstleiter-Bahnhöfe verwenden den normalisierten Bahnhofsnamen als Passwort.

---

### Typen versteckter Bahnhöfe

Für Bahnhöfe ohne menschlichen Fahrdienstleiter stehen zwei Spezialmodi zur Verfügung.

#### Automatisch

Ein automatischer versteckter Bahnhof funktioniert ohne manuelle Interaktion:

- Wenn ein benachbarter Fahrdienstleiter einen Zug zu diesem Bahnhof schickt, wird das Angebot **automatisch angenommen**.
- Sobald der sendende Fahrdienstleiter den Zug als abgefahren markiert, wird die Ankunft des Zuges nach einem konfigurierbaren Timeout als **abgeschlossen** markiert und der Zug dauerhaft aus dem Layout entfernt.
- Wenn ein Nachbarbahnhof einen Zug **von** einem automatischen versteckten Bahnhof erwartet, muss dieser Zug manuell vom Nachbar-Fahrdienstleiter ins Layout eingetragen werden. Er erscheint als vom versteckten Bahnhof abgefahren und belegt den entsprechenden Block.

> [!IMPORTANT]
> Automatische versteckte Bahnhöfe weisen Züge **nicht** automatisch Blöcken zu.

#### Vereinfacht

Ein vereinfachter versteckter Bahnhof ist ein schlankes Frontend, das von Triebfahrzeugführern selbst bedient werden soll — ohne Dispatcher-Kenntnisse. Er zeigt die nächsten 6 Züge und:

- **Bietet den Zug automatisch** dem benachbarten Bahnhof an.
- **Akzeptiert automatisch** Angebote vom benachbarten Bahnhof.
- Ermöglicht es Triebfahrzeugführern, die Ankunft zu bestätigen und den Zug mit einem Tipp aus dem Layout zu entfernen.

Hauptzweck ist es, Triebfahrzeugführern die Verwaltung eigener Fahrten in Abstellbereichen zu ermöglichen, ohne tiefere Kenntnisse von DD-MB zu benötigen.

---

## Magyar

### Követelmények

- A [Grafikon](https://github.com/jub77/grafikon) alkalmazás jub77-től.
- A találkozóhoz tartozó GTM fájl.

---

### Előzetes ellenőrzés

Mielőtt bármilyen exportot generálnál a Grafikonból, ellenőrizd az alábbiakat:

- [ ] Minden emberi forgalomirányítóval rendelkező állomásnak **Elágazó állomás**, **Állomás** vagy **Technikai állomás** típusúnak kell lennie. Ha egy forgalomirányítóval rendelkező állomás típusa **Elágazás**, változtasd meg **Állomás**-ra.
- [ ] Az import és az automatikus blokkfelismerés egyszerűsítése érdekében ellenőrizd az összes állomásrövidítést a Grafikonban (Hálózat nézet). A legegyszerűbb megoldás az állomásnév első három betűjének használata.

---

### 1. lépés — Hangriasztások feltöltése

Alapértelmezetten a DD-MB hat hangriasztást tartalmaz. Ha további hangokra van szükség, töltsd fel őket az adminisztrátori portálon a **Hangkönyvtár** részben. Ugyanitt módosítható a rendszer globális alapértelmezett riasztási hangja is.

---

### 2. lépés — Elrendezés importálása

Az állomásadatokat CSV fájlként exportáld a Grafikonból:

1. A Grafikonban navigálj a **Kimenetek → Kimenetek…** menüpontra.
2. Válaszd a **„text: Állomási menetrendek (CSV) [embedded]"** lehetőséget.
3. Kattints a **Kimenet generálása** gombra.

> [!IMPORTANT]
> Ha a nemzetközi találkozóhoz az állomásneveket vagy megjegyzéseket meghatározott nyelven kell megjeleníteni, a generálás előtt változtasd meg a kimenet nyelvét a Grafikonban. A DD-MB az exportált szöveget változtatás nélkül használja, fordítást nem végez.

Ha az összes CSV export egy mappában van, csomagold őket egyetlen ZIP fájlba.

Jelentkezz be a DD-MB adminisztrátori portálra. Az **Import ZIP** részben válaszd ki a ZIP fájlt, majd kattints a **Feltöltés** gombra. A fájlkiválasztó alatt megjelenik a siker vagy a hiba üzenete.

---

### 3. lépés — Állomások ellenőrzése és konfigurálása

1. Az adminisztrátori portálon nyisd meg az **Állomáskonfiguráció** részt.
2. Fejtsd ki az egyes állomásokat, és ellenőrizd, hogy egyik állomásrövidítés mellett sem jelenik meg a sárga **⚠ unresolved** figyelmeztetés. Ha igen, javítsd ki a blokkmappingokat.
3. Minden állomásnál rendelj szomszédokat a forgalomirányító **Bal** és **Jobb** oldalához. Ha az állomás többvágányos blokkot használ, módosítsd a blokk slotok számát ennek megfelelően.
4. Töltsd ki a **telefonszám**-rövidítést, ha a találkozó telefonos koordinációt alkalmaz.
5. Opcionálisan válassz **alapértelmezett riasztási hangot** minden egyes állomáshoz. A forgalomirányítók a saját nézetükből is megváltoztathatják a riasztási hangjukat.
6. Ha az állomás **rejtett állomás** emberi forgalomirányító nélkül (tárolóhurkok, rendező pályaudvarok stb.), konfiguráld a megfelelő rejtett állomástípust — lásd [Rejtett állomástípusok](#rejtett-állomástípusok) lentebb.
7. Ellenőrizd a **Vágányok** mezőt minden állomásnál. A CSV importból automatikusan töltődik ki a menetrend perronnértékei alapján. Add hozzá a találkozón használt, de a Grafikon adataiban nem szereplő vágányokat.

---

### 4. lépés (Opcionális) — Grafikus menetrendek

Ha grafikus menetrendeket szeretnél a DD-MB-be integrálni, generáld őket a Grafikonban, majd töltsd fel az SVG fájlokat az adminisztrátori portál **Grafikus menetrendek** részébe.

> [!TIP]
> Mindig állítsd be a kimeneti méreteket a Grafikonban úgy, hogy a menetrendek olvashatók legyenek — a DD-MB az SVG fájlokat natív méretükben jeleníti meg, átméretezés nélkül. Lépések: **Kimenetek → Kimenetek… → válaszd az „svg: Grafikus menetrendek [embedded]" lehetőséget → kattints a tulajdonságok ikonra → állítsd be a Szélességet, Magasságot, Zoomot és Max. magasságot**. A megfelelő eredmény eléréséhez általában több próbálkozás szükséges.

---

### 5. lépés (Opcionális) — Forgások / Turnusok

Ha a személyzeti turnusokat a DD-MB-ben szeretnéd nyomon követni, exportáld az összes forgást a Grafikonból (**svg: Forgások grafikus kimenete [embedded]**), és importáld a fájlt az adminisztrátori portál **Turnusok** részébe.

---

### 6. lépés (Opcionális) — Kezdeti konfiguráció exportálása

Jó gyakorlat a teljes állomáskonfiguráció (blokkhozzárendelések, hangok, telefonszámok stb.) azonnali exportálása a beállítás után, hogy teljes meghibásodás vagy visszaállítás esetén gyorsan helyreállítható legyen. Használd az adminisztrátori portál **Export / import konfiguráció** részét a biztonsági mentés létrehozásához és letöltéséhez. A DD-MB bármilyen jövőbeli visszaállítása után a fájl újraimportálása kihagyja a 3. lépés nagy részét.

---

### 7. lépés (Opcionális) — Jelszavak

Egyéni jelszavak állíthatók be az adminisztrátori portálhoz, a Turnusokhoz és az egyes forgalomirányító állomásokhoz:

- Az **adminisztrátori portál** és a **Turnusok** jelszavait az adminisztrátori portál alján, a **Jelszavak** részben lehet beállítani.
- A **forgalomirányító** jelszava állomásonként külön-külön az **Állomáskonfiguráció** részben, az egyes állomások részleteinél adható meg.

Ha nincs egyéni jelszó beállítva, minden szerepkör az alapértelmezett értéket használja: az adminisztrátori portál az `ADMIN_PASSWORD` környezeti változót használja (alapértelmezett: `admin123`), a Turnusok az `ROSTER_PASSWORD` értéket (alapértelmezett: `rosters`), a forgalomirányító állomások pedig a normalizált állomásnevet használják jelszóként.

---

### Rejtett állomástípusok

Az emberi forgalomirányító nélküli állomások számára két speciális üzemmód áll rendelkezésre.

#### Automatikus

Az automatikus rejtett állomás mindenféle kézi beavatkozás nélkül működik:

- Amikor egy szomszédos forgalomirányító vonatot küld erre az állomásra, az ajánlatot **automatikusan elfogadja**.
- Miután a küldő forgalomirányító a vonatot elindítottként jelöli meg, a vonat érkezése egy konfigurálható időkorlát után **befejezettként** van megjelölve, és a vonat véglegesen eltávolításra kerül a layoutból.
- Ha egy szomszédos állomás vonatot vár **az** automatikus rejtett állomástól, azt a vonatot a szomszédos forgalomirányítónak kézzel kell felvennie az elrendezésbe. A rejtett állomásról indítottként jelenik meg, és elfoglalja a megfelelő blokkot.

> [!IMPORTANT]
> Az automatikus rejtett állomások **nem rendelik hozzá** automatikusan a vonatokat a blokkokhoz.

#### Egyszerűsített

Az egyszerűsített rejtett állomás egy könnyű felhasználói felület, amelyet maguk a mozdonyvezetők kezelhetnek — forgalomirányítói ismeretek nélkül. A következő 6 vonatot jeleníti meg, és:

- **Automatikusan ajánlja** a vonatot a szomszédos állomásnak.
- **Automatikusan elfogadja** a szomszédos állomástól érkező ajánlatokat.
- Lehetővé teszi a mozdonyvezetők számára, hogy egyetlen koppintással megerősítsék az érkezést és eltávolítsák a vonatot az elrendezésből.

A fő cél az, hogy a mozdonyvezetők a tárolóterületen kezelhessék saját meneteiket a DD-MB mélyebb ismerete nélkül.
