## 01 - Vrstva síťového přístupu, Ethernet
----

#### Protokol IEEE 802.3

- firma Institute of Electrical and Electroncs Engineers
- použit v LAN
- standard, který určuje specifikace spojové a fyzické vrstvy
  - vznikl z důvodu standardizace lokálních sítí
- standard udává typ kabelu a přenosovou rychlost

#### MAC vrstva

- Media Access Control
- spodní část spojové vrstvy (podvrstva)
- řídí přístup k médiu
- zapozdřuje data
  - ohraničení rámců
  - adresace (MAC adresa)
- je hardwarově závislá

#### LLC vrstva

- Logical Link Control
- vrchní část spojové vrstvy (podvrstva)
- řídí bezpečný přenos dat
- poskytuje multiplex (více síťových protokolů v síti)
- není hardwarově závislá

#### Protokol IEEE 802.2

- standard, který definuje řízení LLC
- umožňuje LLC pracovat jako horní podvrstva spojové vrstvy

#### Způsoby posílání packetů

- určují, kdo je příjemce dat

##### Unicast

- posílá data na jednu cílovou adresu

##### Multicast

- posílá data na všechny zařízení z určité skupiny

##### Broadcast

- posílá data všem zažízením v síti

##### Anycast

- speciální verze multicastu
- packet si vybírá pouze určité zařízení ze skupiny a nejvýhodnější cestu k němu

#### ARP protokol

- Address Resolution Protocol
- používá se v případě, kdy známe pouze IP adresu daného zařízení

**Postup:**

1. zařízení vyšle broadcast s cílovou adresou - nazývá se **ARP request**
2. příjemce vyhodnotí, že se jedná o něj, pošle zpět **ARP reply**
3. ARP reply obsahuje MAC adresu cílového zařízení

- všechna zařízení v síti si v případě příchodu ARP requestu zapisují data do své cache

#### Ethernetový rámec

- obaluje packet
- po naplnění packetu všemi daty se zabalí do rámce a putuje sítí

**Obsahuje:**
- preambuli (identifikuje začátek rámce)
- hlavičku (obsahuje zdrojové a cílové adresy)
- data (max 1500 oktetů)
- kontrolní posloupnost rámce (kontrolní součet dat)
- mezeru mezi packety (časový interval, kdy nic nesmí vysílat - odděluje packety)

##### PPP
- Point to Point Protocol
- definuje komunikaci mezi dvěma body
- obsahuje dynamické nastavování klienta, autentizaci, šifrování dat

----

#### Typy kabelů

- STP/UTP kabely většinou obsahují RJ45 konektor

##### Koaxiální
- vodivé jádro, izolace, měděná síť, vnější izolace
- antény, mikrofony

##### UTP
- Unshielded Twisted Pair
- nestíněná dvoulinka
- 4 páry vodičů, izolované a kroucené

##### STP
- Shielded Twisted Pair
- stíněná dvoulinka
- 4 páry vodičů, izolované a kroucené
- díky stínění omezuje elektrický šum

##### Optický
- vlákno, které je uvnitř sklěnené/plastové
- odráží se v něm paprsek
- nejrychlejší
- neovlivní ho elektromagnetické rušení
