## 11 - Základní desky
----

#### Základní deska
- nezbytná součást každého počítače
- spojuje komponenty dohromady a umožňuje, aby spolu mohly komunikovat
- rozvádí napájení ze zdroje
- některé komponenty jsou integrované (síťová, zvuková karta), ostatní jsou připojeny pomocí sběrnic
- na základní desce se nachází BIOS a chipset
  - Basic Input Output System

##### Chipset
- více integrovaných obvodů, které zajišťují komunikaci mezi CPU, pamětí a periferiemi
- v dnešní době jde o integrovaný jižní a severní můstek dohromady
- příklady:
  - Intel Z490
  - AMD B550

##### BIOS
- Basic Input Output System
- implementuje základní vstupně výstupní funkce počítače
- jedná se o firmware
- uložen v EEPROM / flash paměti na základní desce
- při startu počítače se spustí BIOS a proběhne inicializace a test komponent

##### UEFI
- Unified Extensible Firmware Interface
- nástupce BIOSu
- obsahuje GUI místo textu
- navíc obsahuje další pokročilejší funkce (Secure Boot, kontrola malware)
- základní funkce stejné jako BIOS

##### Patice (socket)
- slot pro připojení CPU k základní desce
- CPU nevyžaduje připojení napájení kabelem, napájí ho patice
- dělí se na:
  - **PGA**
    - Pin Grid Aray
    - na spodní straně jsou piny, které se zapojí do socketu
    - používá ho AMD
    - AMD AM4
  - **LGA**
    - Land Grid Aray
    - na spodní straně jsou plošinky, které se zapojí do socketu
    - používá ho především Intel
    - Intel 1151

##### Severní můstek (northbridge)
- připojen přímo k CPU
- zajišťuje komunikaci mezi CPU, RAM a sběrnicemi PCI, PCI-e
- spojuje CPU se severním můstkem
- většina funkcí jižního můstku je nyní již implementována přímo do CPU

##### Jižní můstek (southbridge)
- též nazýván chipset
- propojuje audio, ethernet, sběrnice USB, SATA a BIOS chip
- dříve byl propojen s jižním můstkem přes PCI sběrnici

##### Formát desky
- **vybírá se podle:**
  - velikosti a kompatibility se skříní
  - rozložení montážních šroubů
  - typ zdroje
  - počtu slotů pro přídavné karty
- **příklady formátů:**
  - ATX, MicroATX, MiniITX
- nejpoužívanější - **ATX**
  - Advanced Technology eXtended
  - od Intelu

##### RAM slot
- **typy:**
  - SIMM
    - Single In-Line Memory Module
    - zdvojený kontakt na obou stranách
  - DIMM
    - Dual In-Line Memory Module
    - samostatné kontakty na obou stranách
  - SO-DIMM
    - Small Outline Dual In-Line Memory Module
    - upravená verze pro notebooky
- RAM lze připojit do Dual-Channelu
  - barevně rozlišeno na desce
  - teoretické zdvojnásobení propustnosti dat

#### Interní sběrnice
##### ISA
  - Industry Standard Architecture
  - zastaralá, jednoduchá
  - max 16bit, nízká rychlost
  - později nahrazena novějšími
##### PCI
  - Peripheral Component Interconnect
  - inteligentní, spolupracuje s mikroprocesorem
  - max 64bit, frekvence až 133MHz
  - její řadič posílá data maximální možnou frekvencí, která se mění

##### PCI-E
  - Peripheral Component Interconnect Express
  - na rozdíl od jejích předchůdců je seriová
  - stromová topologie
  - nejpoužívanější sběrnice, standard pro grafické karty
    - další zařízení - síťové karty, zvukové karty, USB karty
  - má několik verzí, které se liší velikostí a rychlostí
  - nejznámější:
    - PCI-E x1
    - PCI-E x16

#### Externí sběrnice
##### USB
- Univeral Serial Bus
- sériová sběrnice pro připojení periferií
  - tiskárny, myši, klávesnice, fotoaparáty, externí disky, gamepady...
- Plug & Play
  - lze připojovat a odpojovat zařízení za běhu PC
- má několik verzí, nejnovější je USB-C (2013)
  - u verze C se nemusí rozlišovat orientace konektoru
  - časem se má stát standardem všech zařízení
- přes USB lze i napájet

##### FireWire
- sériová sběrnice navržena společností Apple
- jednoduchá, levná
- méně rozšířený než USB
- pro připojení digitálních videokamer, optických mechanik, externích disků
