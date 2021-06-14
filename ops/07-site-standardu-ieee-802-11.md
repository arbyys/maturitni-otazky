## 07 - Sítě standardu IEEE 802.11
----

- WiFi standard
- různe verze standardu (doplňky)
  - druhy modulace pro posílání signálu
- všechny verze používají stejný protokol

Název | Označení | Pásmo [GHz] | Maximální rychlost [MBit/s] | Charakteristika
:----:|:--------:|:-----------:|:---------------------------:|:--------------:
původní IEEE 802.11 | - | **2.4** | **2** | -
IEEE 802.11a | Wi-Fi 2 | **5** | **54** | méně vytížené kmitočtové pásmo, více kanálů
IEEE 802.11b | Wi-Fi 1 | **2.4** | **11** | dynamicky se mění rychlost podle momentálního rušení
IEEE 802.11g | Wi-Fi 3 | **2.4** | **54** | obdoba 802.11a, ovšem pro pásmo 2.4GHz
IEEE 802.11n | Wi-Fi 4 | **2.4**, **5** | **600** | větší rychlost díky MIMO, upravuje MAC podvrstvu
IEEE 802.11ac | Wi-Fi 5 | **2.4, 5** | **3 466.8** | větší šířka pásma
IEEE 802.11ax | Wi-Fi 6 | **2.4**, **5**, **6** | **10 530** | zlepšení spolehlivosti sítě

----

#### Přenosová trasa
- **drátové sítě** - telefonní linka / koaxiální kabel / rádiový přenos
- **bezdrátové sítě** - optické záření / mikrovlnné záření

#### DCF
- Distributed Coordination Function
- základní přístupová metoda k médiu
- postavena na CSMA/CA
  - protokol s vícenásobným přístupem a nasloucháním nosné
- naslouchá, zda je médium volné - pokud je, tak vyšle packet
- nevýhoda - u velkého počtu stanic stoupá pravděpodobnost kolize

#### PCF
- Port Coordination Function
- dodatečná přístupová metoda k médiu
- využívá se, pokud jsou stanice přípojeny jako Access Point
- AP přiděluje přenosové médium registrovaným žadatelům

#### Wi-Fi
- několik standardů IEEE 802.11
- popisuje bezdrátovou komunikaci v sítích
- zajišťuje komunikaci na L2 (spojové vrstvě)
- přenášejí se zapouzdřené ethernetové rámce

#### Struktury bezdrátových sítí
##### Ad-hoc sítě
- navzájem spojuje dva klienty
- jsou v rovnocenné pozici
  - Peer-to-Peer
- identifikace pomocí SSID
- oba klienti musí být vzájemně v přímém dosahu
- použito pro menší sítě / příležitostné spojení

##### WiFi Direct
- propojení několika zařízení bez nutnosti použití Access Pointu
- stačí, když má WiFi Direct pouze jedno zařízení
- spojení je Peer-to-Peer
- může nahradit Bluetooth

##### Infrastrukturní sítě
- obsahuje jeden nebo více Access Pointů
- klient si vybírá podle názvu, ke kterému Access Pointu se připojí
- Access Pointy můžou mít stejné SSID
  - poté se klient připojí k nejbližšímu

#### Access Point (AP)
- řídí komunikaci mezi Wi-Fi zařízeními
- slouží jako vstup do sítě
- lze je použít pro poskytování různých služeb

#### MIMO
- Multiple-input multiple-output
- abstraktní matematický model pro multi-anténní systémy
- zvyšuje velikost datové propustnosti
  - vyšší rychlost
- zefektivňuje využití rádiových systémů

#### OFDM
- Orthogonal Frequency Division Multiplexing
- širokopásmová **modulace**
- využívá frekvenční dělení kanálu

#### QAM
- Quadrature Amplitude Modulation
- amplitudová **modulace**
- využívá zvýšení maximálního kmitočtu telefonního signálu

#### Zabezpečení sítě
- různé způsoby ochrany sítě před útočníky
- zastaralé metody se na nových zařízeních nepoužívají

##### Kontrola MAC adres (zastaralá)
- Access Point obsahuje seznam MAC adres, kterým je povolen přístup do sítě
- whitelist / blacklist

##### WEP (zastaralá)
- Wired Equivalent Privacy
- statické klíče symetrické šifry
- ručně nastaveny na obou stranách spojení

##### WPA (zastaralá)
- Wifi Protected Access
- využívá stejné klíče jako WEP
  - jsou ovšem dynamicky měněny
- k autentizaci se využívá:
  - **Pre-Shared Key** - obě strany mají stejnou heslovou frázi
  - **RADIUS server** - centralizované zabezepeční z databáze - jménem a heslem

##### WPA2
- novější verze WPA
- vyžaduje větší výkon, nelze použít na starých zařízeních
- kvalitnější šifrování (AES)

##### EAP
- autentizační rámec
- přenáší klíče, které se generují podle metod z RFC 3748
- definuje formáty zpráv, nejde o protokol
