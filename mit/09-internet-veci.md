## 09 - Internet věcí
----

#### IoT
- Internet of Things
- síť propojených objektů, které jsou jednoznačně adresovatelné a tvoří síť
- síť těchto objektů je založena na komunikačních protokolech, které umožňují výměnu dat
  - analýzou těchto dat lze dosáhnout vyšší přidané hodnoty
- IoT se snaží data v Internetu získávat z připojených senzorů místo toho, aby je zadávali lidé
  - v roce 2008 překročil počet připojených zařízení k internetu počet světové populace, do této doby se datuje vznik IoT
- cíl IoT je propojení systému dohromady, jejich data se poté dají různě využít
- rozdělen na:
  - **PAN**
    - Personal Area Network
    - osobní elektronika, lokální zařízení
    - Bluetooth
  - **WLAN**
    - chytrá domácnost, firma
    - více zařízení, větší prostor
    - WiFi
  - **LPWAN**
    - majitel zařízení si pouze pronajímá infrastrukturu
      - není provozovatelem
    - LoRaWAN, Sigfox, NB-IoT

##### Požadavky na IoT
- sběr dat
- uložení dat
- analýza dat
- sdílení výsledků
- bezpečnost
- zpracování velkých objemů dat

##### Spotřebitelský IoT
- zlepšení uživatelského zážitku
- systémy nejsou nutné
- zjednodušení každodenního života
- spotřebitelských zařízení v IoT **není tolik**, jako průmyslových
- **použití:**
  - chytré domácnosti
    - dálkové ovládání spotřebičů, detekce otevření dverí, monitorování elektrické energie
  - inteligentní nakupování
    - rady při nákupu podle preferencí, zvyků, alergií apod.
  - jednodušší platby (mobilem)
    - NFC čipy

##### Průmyslový IoT
- použití chytrých zařízení v průmyslových oblastech
- efektivnější využívání zdrojů
- zvýšení pracovní produktivity
- zvýšení bezpečnosti pracovniků
- předcházení vypadkům systému
- tento segment je **převládající**
- **použití:**
  - průmyslová automatizace
    - automatická diagnostika přístrojů
  - dopravní průmysl
    - automaticky řízené automobily
  - energetický průmysl
    - monitorování spotřeby energie

#### Architektura
##### Hardware
- fyzické systémy
- generují data, komunikují
- datová uložiště
- senzory

##### Middleware
- softwarová mezivrstva
- poskytuje rozhraní aplikací
- umožňuje propojení dvou vrstev a jejich komunikaci

##### Software
- použit pro analýzu, skládání a kombinování dat
- cloudové úložiště
  - budou zásadní pro všechny systémy
- prezentace výsledků, zobrazení hodnot

#### Sítě typu LPWAN
- tři odlišné technologie připojení v ČR
##### LoRaWAN
- firma CRA
  - česká radiokomunikace
- využívá rádiovou komunikaci
- pro přenos menšího množství informací na velkou vzdálenost
- nízká energetická náročnost
- dobrá bezpečnost
- obousměrná komunikace

##### Sigfox
- firma SimpleCell
- nízká rychlost
- nízká energetická náročnost
- omezení maxima zpráv pro jedno zařízení za den
- hodí se více na jednosměrnou komunikaci
  - obousměrná komunikace je omezená

##### NB-IoT
- O2, Vodafone, T-Mobile
  - mobilní operátoři
- náročnější na spotřebu
- nejvyšší rychlost
- zařízení musí obsahovat SIM kartu

#### Komunikační protokol
- protokol MQTT
  - Message Queue Telemetry Transport
- typicky používá TCP
- určen pro výměnu dat na vzdálená místa

##### Publisher
- poskytovatel zpráv
- komunikuje s brokerem

##### Broker
- centrální bod komunikace
- navazuje s publisherem a subscriberem komunikaci, vyměňuje mezi nimi data
- prostředník
- komunikuje s publisherem a subscriberem

##### Subscriber
- příjemce zpráv
- komunikuje s brokerem
- může přijímat data od více publisherů

##### Topic
- téma dané zprávy
- mají stromovou podobu
