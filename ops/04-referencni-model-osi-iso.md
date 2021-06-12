## 04 - Referenční model OSI/ISO
----

- Open System Interconnection/International Standards Organization
- dělí vzájemnou komunikaci mezi počítači mezi 7 vrstev
- každá vrstva vykoná příslušnou činnost a předá data další vrstvě
  - každá vrstva neví, jak data zpracovala předchozí vrstva - nepotřebuje to vědět
- přenos dat mezi vrstvami je pomocí packetů
- pokud daná vrstva není potřebná, je implementována jako prázdná
- některé vrstvy se dělí na podvrstvy
- začátek je na aplikační vrstvě

![Obrázek vrstev](https://docplayer.cz/docs-images/54/8616084/images/page_6.jpg)

#### 1) Fyzická vrstva:
##### Physical layer

- spravuje fyzické připojení
- zodpovědná za přenos nestrukurovaných dat
- nekontroluje význam bitů, pouze je přenáší přes signály
- chyby hlásí spojové vrstvě
- **repeater, hub, kabel**

#### 2) Spojová vrstva:
##### Data link layer
- někdy nazývána linková
- formátuje data do rámců
  - ty poté posílá dál
- zajišťuje bezchybný přenos dat mezi stanicemi
- dělí se na LLC (horní podvrstva) a MAC (spodní podvrstva)
- **bridge, switch**

#### 3) Síťová vrstva:
##### Network layer
- definuje protokoly pro směrování dat a jejich adresaci
- volí, kterou cestou by packety měly putovat
- zajišťuje celkový přenos dat v síti
- nese informace o problémech při doručování dat
- **router, L3 switch**

#### 4) Transportní vrstva:
##### Transport layer
- rozhodne o způsobu přenosu dat - paralelně / jednou cestou
- provádí multiplexing, rozdělování dat, kontrolu chyb
- dostane data od relační vrstvy, rozdělí ji na menší jednotky a předá network vrstvě
- zajišťuje přenos dat mezi vrstvami
- porty, tcp/udp
- **gateway, firewall, TCP/UDP**

#### 5) Relační vrstva:
##### Session layer
- spravuje komunikaci mezi dvěma aplikacemi
- stará se o přihlašování, zabezpečení
- zabezpečuje výměnu dat mezi dvěma aplikacemi bez problémů
- data sychnronizuje, aby nedošlo ke ztrátě dat
- **NetBIOS, PC**

#### 6) Prezentační vrstva:
##### Presentation layer
- konvertuje data do podoby, kterou používají aplikace
- zabývá se pouze strukturou dat, nikoliv jejich významem
- kóduje, komprimuje, šifruje, hashuje...
- **ASCII kódování, PC**

#### 7) Aplikační vrstva:
##### Application layer
- nejvrchnější vrstva
- poskytuje aplikaci přístup ke komunikačnímu systému
- identifikace komunikace, přenos zpráv, synchronizace aplikací
- vrstvu představují konkrétní aplikace
- **FTP, SSH, POP3**

----

#### PDU
- Protocol Data Unit
- při postupném procházení jednotlivými vrstvami se sem přidávají různé informace
- každé vrstva přidá svou specifickou informaci
- v každé vrstvě má jiný název:
  1) ve fyzické - **bity**
  2) v linkové - **rámec**
  3) v síťové - **packet**
  4) v transportní - **TCP segment / UDP datagram**
  5) v relační - **data**
  6) v prezentační - **data**
  7) v aplikační - **data**

#### Zapouzdření
- vložení PDU z vyšší vrstvy do těla dat
- každá vrstva si z PDU vezme pouze informaci, které jí náleží
- redundance dat, řízení toku

#### OSI / ISO vs TCP / IP
- v TCP / IP je fyzická a spojová vrstva v jednom
- v TCP / IP je aplikační, prezentační a relační v jednom
- TCP / IP je rychlejší, ovšem méně spolehlivé
- TCP / IP bere, že spolehlivost musí zařídit koncoví učastníci komunikace
  - **TCP / IP - jednodušší, méně spolehlivé**
  - **OSI / ISO - složitější, detailnější, spolehlivější**

![Srovnání](https://lh3.googleusercontent.com/proxy/C3F3rOZ_NfIicdK-VBxN0PUzOFEjzd_cA9dQXpkPvpWoE2ktfJmC02_bHtoAjgMW8clBEVMS5U4RsLfj)

----

#### Aktivní prvky v síti

##### Hub (rozbočovač):
- **fyzická vrstva**
- všechna data, která přijdou na nějaký port, zkopíruje na všechny ostatní porty
- vysílá broadcast
- velmi jednoduchý
- přetěžuje síť (prvky musí filtrovat pouze ty data, co jsou pro ně určené)

##### Repeater (opakovač):
- **fyzická vrstva**
- příjímá zkreslený / poškozený signál, opraví ho a posílá dál
- neumí data nijak filtrovat
- posílá data broadcastem dál

##### Bridge (most):
- **spojová vrstva**
- "switch, co má pouze dva porty"
- spojuje 2 části sítě
- sestaví si tabulku s porty MAC adres z obou částí sítě
- když přijde packet, podle cílové adresy ho buď pošle na druhou stranu, nebo vyřadí
  - snižuje se provoz v síti, pokud se posílají packety přes broadcast všem
- když není adresa v tabulce, pošle packet broadcastem

##### Access point (přístupový bod)
- **spojová vrstva**
- zkratka AP
- poskytuje klientům vstup do sítě
- typicky připojení přes Wi-Fi

##### Switch (přepínač):
- **spojová vrstva**
- "chytřejší hub"
- analyzuje packety a posílá je na port, kam přísluší
- pokud switch neví, pošle broadcast na všechny porty
  - poté dostane odpověď, který port byl ten správný
  - postupně se učí, které porty mají jaké MAC adresy
- tyto informace ukládá do CAM tabulky

##### Router (směrovač):
- **síťová vrstva**
- spojuje více sítí dohromady
- používá routovací tabulku a hledá nejlepší cestu packetu
- v lokální sítí je router gateway
- pokud router neví, kam packet odeslat, zahodí ho
