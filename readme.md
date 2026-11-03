# HAVAS: KLÓNPROTOKOLL

**Verzió:** 1.1 · **Nyelv:** C# · **Felület:** Windows Forms · **Célkeretrendszer:** .NET Framework 4.8

**Havas Attila az eredeti. Mindenki más csak másolat.**

C# Windows Forms aréna-akciójáték Havas Attila főszereplésével, a feltöltött portrék felhasználásával. A képeket és a programikonját az EXE tartalmazza. Nincs NuGet-csomag, játékmotor, internetkapcsolat vagy külön letöltendő grafikai elem.

**1.1-es változat:** két új, a feltöltött képekkel megjelenő vendégellenfél került a játékba. **Alkoholista** forgó, zöld, narancssárga címkés Jäger-üvegeket lő Havas Attilára. **Mama** három repülő protkót dob egyszerre, legyező alakban. Mindketten már az első hullámban megjelennek, majd a további hullámokban is visszatérnek. A pillérek blokkolják az új lövedékeket, a Havas-pulzus pedig eltünteti őket. A nevek fiktív játékszerepeket jelölnek.

## Indítás Visual Studióban

1. Csomagold ki **az egész ZIP-et** egy mappába.
2. Nyisd meg a **HavasKlonprotokoll.sln** fájlt Visual Studióban.
3. Szükséges összetevők: **.NET asztali fejlesztés** és **.NET Framework 4.8 célzócsomag / fejlesztői csomag**. Ezeket a Visual Studio Installerben tudod hozzáadni. A projekt Windows Forms / .NET Framework projekt.
4. A Solution Explorerben a HavasKlonprotokoll projekten jobb gomb → **Set as Startup Project**, ha szükséges.
5. Nyomj **F5**-öt vagy **Ctrl+F5**-öt.

Windows 10/11 és Visual Studio 2022 vagy újabb használható a megfelelő .NET Framework összetevőkkel. A projekt AnyCPU; nem szükséges x64-re átállítani. A Form és a teljes felület C#-ból épül fel, nincs külön Form1.Designer.cs.

## Azonnali indítás fordítás nélkül

A **bin/Release/HavasKlonprotokoll.exe** a lefordított játék. Windows alatt indítsd dupla kattintással; a mellette lévő **HavasKlonprotokoll.exe.config** maradjon vele. .NET Framework 4.8 futtatókörnyezet szükséges. Saját módosításhoz nyisd meg a solutiont, szerkeszd a C# fájlokat, majd fordítsd újra a projektet.

Alternatíva: **Forditas.cmd** a Windows beépített .NET Framework C# fordítójával készít új EXE-t, Visual Studio nélkül. A normál fejlesztési út a solution és az F5.

## A játék

Egy fiktív sci-fi klónlaborban Havas Attila másolatai önállósodtak. Az eredeti operátorként 15 hullámon keresztül kell leállítanod a hálózatot. A történet és a Havas Industries elnevezés kitalált játékelem.

- **3 azonnal elérhető fegyver:** automata karabély, hétszemes sörétes, több ellenfélen átütő sínpuska.
- **5 klóntípus:** alapklón, gyors rohamklón, távolsági lövész, nagy életű titán, kétfelé osztódó klón.
- **2 vendégellenfél:** Alkoholista saját üveglövedékekkel és Mama saját protkóival, külön portréval és harci viselkedéssel.
- **Havas Prím főellenfél:** az 5., 10. és 15. hullámban. Körkörös lövedékek, előre jelzett robbanászónák, második fázis és rohamtámadás.
- **13 fejlesztés:** hullámok között három véletlen modul közül választhatsz. A bónuszok az adott futam végéig maradnak meg.
- **Dash és Havas-pulzus:** a dash rövid sérthetetlenséget ad; a pulzus területet sebez és eltünteti a közeli ellenséges lövedékeket.
- **Operátor és Hardcore mód**, kombóval növekvő pontszorzó, élet-, lőszer- és energiafelvétel.
- Részecskék, becsapódási effektek, képernyőrázás, szintetizált hangeffektek, teljes képernyő, automatikus szünet ablakváltáskor.
- **A portré a menüben, a főhősön, minden klónon, a főellenfélen, a fejlesztési kártyákon, a HUD-on és az aréna termináljain is megjelenik.**

## Irányítás

| Gomb | Művelet |
|---|---|
| WASD vagy nyilak | Mozgás |
| Egér | Célzás |
| Bal egérgomb nyomva | Folyamatos lövés |
| 1 / 2 / 3 vagy egérgörgő | Fegyverváltás |
| R | Újratöltés |
| Space / Shift / jobb egérgomb | Dash |
| Q | Havas-pulzus 100 energiánál |
| 1 / 2 / 3 a fejlesztésképernyőn | Fejlesztés választása |
| Esc | Szünet / folytatás; a főmenüben kilépés |
| F11 | Teljes képernyő váltása |
| M | Hang ki/be |
| Enter a főmenüben / eredménynél | Indítás / új futam |

## Taktika

A tartalék lőszer korlátlan, de a tárak végesek. Fegyverváltáskor az éppen futó újratöltés megszakad. A pillérek blokkolják a mozgást és mindkét fél lövedékeit. A dash sem visz át a pilléreken. A piros körök a főellenfél hamarosan becsapódó támadásait jelölik: térj ki belőlük. A villogó, megjelenő ellenfelek rövid türelmi időt adnak.

Hullám végén a megmaradt felvehető tárgyak automatikusan begyűlnek, a tárak feltöltődnek és kapsz némi életet. A pulzushoz szükséges energia klónok kiiktatásával és energiafelvétellel töltődik. A 15. hullám összes ellenfelének legyőzése győzelmet ad. Halálkor új futamot kell indítani.

## Mentés

A rekordok és a hangbeállítás automatikusan ide kerülnek:

`%LOCALAPPDATA%\HavasKlonprotokoll\profile.xml`

A két nehézségi szintnek külön pontrekordja van. Futam közbeni állapotmentés nincs; az újrakezdés, főmenübe lépés és bezárás megszakítja az aktuális futamot. Sérült vagy nem írható profil esetén a játék továbbra is elindul. A mentési mappa törlésével a rekordok nullázhatók.

## A forrás felépítése

| Fájl | Tartalom |
|---|---|
| Program.cs | Belépési pont és hibajelzés |
| GameForm.cs | Windows Forms ablak, vezérlés, 120 Hz-es szimulációs ciklus, képernyőállapotok |
| Simulation.cs | Mozgás, fegyverek, ellenfelek, főellenfél, ütközések, hullámok és fejlesztések |
| Rendering.cs | Teljes saját rajzolású GDI+ felület, HUD és effektek |
| Model.cs | Vektorok és játékelemek adattípusai |
| Audio.cs | Külső hangfájlok nélküli PCM hangeffektek |
| Profile.cs | Helyi XML-profil mentése |
| Assets | Havas Attila, Alkoholista és Mama beágyazott portréi és a programikon |
| tests | Játékmeneti ellenőrzések és Windows tesztindító |
| Kepernyokepek | A valódi C# renderelővel készített előnézetek |

A beállítások a World osztály elején módosíthatók; a fegyverparaméterek a `Weapons` tömbben, a hullámok száma a `LastWave` állandóban található.

## Tesztek futtatása

A projekt főmappájából vagy a fájlokra dupla kattintva:

- `tests/Tesztek.cmd`: játékmeneti tesztek.
- `tests/FeluletTeszt.cmd`: WinForms integrációs ellenőrzések; ehhez előbb a játék Release változatát kell lefordítani.

Az eredmények a tesztablakban jelennek meg. A csomaghoz mellékelt ellenőrzések kimenete a `tests/simulation-results.txt` és a `tests/ui-results.txt` fájlokban található.

## Gyakoribb indítási problémák

| Jelenség | Megoldás |
|---|---|
| A Visual Studio nem találja a .NET Framework 4.8 referencia-összeállításait. | Telepítsd a .NET Framework 4.8 célzócsomagot vagy fejlesztői csomagot a Visual Studio Installerből. |
| A projekt vagy a Windows Forms összetevő nem tölthető be. | Ellenőrizd, hogy a .NET asztali fejlesztés munkaterhelés telepítve van-e. |
| F5-re másik projekt indul el. | Állítsd a HavasKlonprotokoll projektet indítási projektnek. |
| A portrék hiányára hivatkozó fordítási hiba jelenik meg. | Csomagold ki a teljes projektet, az `Assets` mappával együtt. A képeket a projekt beágyazott erőforrásként használja. |
| Nincs hang. | Az M billentyűvel kapcsold be a hangot, majd ellenőrizd a Windows hangerőkeverőjét. |

Váratlan alkalmazáshibánál a részletes napló helye: `%TEMP%\HavasKlonprotokoll-error.log`.

## Ellenőrzés és korlátok

A projekt sikeresen lefordult; 32 játékmeneti és 17 WinForms integrációs ellenőrzés sikeres eredménnyel lefutott. A fő képernyőkről a játék saját rajzolójával készültek előnézeti képek. A részletes ellenőrzési lista az **ELLENORZES.md** fájlban van. Az ellenőrzés Linux/Mono környezetben történt, natív Windows/Visual Studio futtatás itt nem volt elérhető. Windowsos hangkimenet és DPI-kezelés ezért külön kézi ellenőrzést igényelhet.

A játék egy komplett, egyarénás 2D projekt; a felülete GDI+-szal készül. A hangmotor rövid hangeffekteket játszik le, nem többsávos zenemotor. Külső eszközt vagy 3D motort nem használ.
