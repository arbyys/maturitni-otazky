## 08 - Protokol TCP, UDP
----

### TCP
#### Obecné informace
- Transmission Control Protocol
- přenosový protokol
  - vytváří spojení, přes které lze obousměrně přenášet data
- transportní vrstva OSI/ISO modelu (L4)
- **data jsou doručena spolehlivě a ve správném pořadí**
- TCP využívá služby protokolu IP, který rozšiřuje o kontrolu dat

##### Použití
- E-Mail, SSH, WWW
  - služby, kde data musí dorazit vždy v celku

#### Způsob funkce
1. zařízení A pošle informaci zařízení B, že se chystá přenášet data
2. zařízení si navzájem sychronizují informace o přenosu
3. zařízení A pošle data
4. zařízení B vráti informace, co všechno dostal (po určité době)
5. zařízení A zkontroluje informace
6. pokud některé informace nedorazily, zařízení A je pošle znova
7. proces se opakuje, dokud všechna data nadorazí bezpečně do cíle
8. pokud všechna data přijdou a zařízení A to potvrdí, **spojení může zaniknout**

#### Výhody
- spolehlivost, kontrola dat, potvrzení
- zajištění správného pořadí dat
- data posílá dokola, dokud nejsou doručena

#### Nevýhody
- blokuje frontu (neposílá další data, než jsou doručena předchozí)
- nevhodný pro real-time aplikace
- hlavička obsahuje velké množství informací
- velká zátěž pro síť

----

### UDP
#### Obecné informace
- User Datagram Protocol
- přenosový protokol
  - vytváří spojení, přes které lze obousměrně přenášet data
- transportní vrstva OSI/ISO modelu (L4)
- **nezračuje doručení dat, odesílatel nepotřebuje odpověď**
- nevytváří spojení mezi hostiteli
- komunikuje vždy pomocí portů
- využívá protokol IP, multiplexuje datagramy
  - rozlišování různých příjemců / odesíletelů dle čísla portu

##### Použití
- real-time aplikace, videohovory, online hry
  - aplikace, kde nevadí, že občas nějaká data nepřijdou

#### Výhody
- vysoká rychlost
- méně dat v hlavičce
- malé zatížení sítě

#### Nevýhody
- nezaručuje doručení dat
- neposílá znovu data, co se nedoručí
- nezajišťuje správné pořadí dat
- nezabezpečený přenos dat

----

#### Plovoucí okno
- mechanismus TCP protokolu
- zvýšení plynulosti transportu dat
- velikost okna se dynamicky mění
- odesílatel udává, **kolik bitů chce ještě odeslat**
- příjemce udává, **kolik bitů je schopen přijat**

#### Přepínání datagramů
- data jsou rozděleny na menší části
- v síti je směrují síťové prvky jako switch / router
- až když dorazí k příjemci, jsou seřazeny

#### Přepínání obvodů
- "Circuit switching"
- obvod mezi dvěma zařízeními
- obvod vybere jednu z možných cest mezi zařízeními
  - právě touto cestou posílá všechny datagramy

#### Omezení režie
- omezeni velikosti odesílaného datagramu

----

### Porty
- port naslouchá

#### 1 - 1023
- Well known (dobře známé) porty
- vyhrazené, pro typicky používané aplikace

Číslo portu | Služba
:----------:|:-----:
20 | FTP (data)
21 | FTP (příkazy)
22 | SSH
23 | Telnet
53 | DNS
67 | DHCP (server)
68 | DHCP (klient)
80 | HTTP
143 | IMAP
443 | HTTPS
666 | hra Doom


#### 1024 - 49151
- Registrované porty
- jejich použití se musí registrovat u ICANN

#### 49152 - 65535
- Soukromé a dynamické porty
- pro soukromé využití
- nejsou pevně přiděleny žádné službě
