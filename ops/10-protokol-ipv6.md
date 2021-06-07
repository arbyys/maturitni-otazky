## 10 - Protokol IPv6
----

#### Specifikace
- následník IPv4
- 128 bitů
- spadá do L3 modelu OSI/ISO (síťová vrstva)
- 340 undecilionů adres
- bezpečnost
- obsahuje tři druhy adres - **unicast**, **multicast** a **anycast**
  - **neobsahuje broadcast**

#### Rozdíly IPv4 vs IPv6
##### IPv4
- části odděleny tečkou
- čísla v desítkové soustavě
- má 4 oktety (oktet = byte)
- adresní prostor je 32 bitů

##### IPv6
- části odděleny dvojtečkou
- čísla v hexadecimální soustavě
- má 8 hextetů (hextet = 4 hexadecimální čísla)
- adresní prostor je 128 bitů

#### Dual-Stack
- duální implementace obou verzí IP adresy
- takto se nazývá host, co implementuje obě adresy
- obsahuje zásobníky protokolu pro IPv4 a IPv6

#### NAT64
- mechanismus, který usnadňuje přechod od IPv4 na IPv6
- vzájemný překlad datagramů, aby mohla komunikovat i zařízení s odlišnými verzemi adres
- zajišťuje přístup k IPv4 internetu pro stroje s adresou IPv6
  - druhým směrem lze komunikovat pouze velmi omezeně

#### Tunel
- zabalení protokolu do druhého
- tuneluje se IPv6 datagram aby prošel IPv4 sítí
- tím se "zamaskuje", že jde ve skutečnosti o IPv6 datagram
  - bez problémů projde IPv4 sítí

#### SLACC
- Stateless address autoconfiguration
- host se automaticky konfiguruje v síti
- po připojení posílá svou adresu pro konfiguraci informací (multicastem)

#### Prefix
- shodné nejvýznamější bity v adrese vlevo
  - v jedné síti / podsíti
- velikost prefixu je dána CIDR
  - Classless Inter-Domain Routing
- doporučená velikost podsítě je **/64**
  - aby fungoval NDP protokol
- délka prefixu určuje, jaká část adresy je pouze adresa podsítě a nikoliv adresa zažízení

#### Komprimace nul
- pokud adresa obsahuje dlouhou posloupnost nul, lze ji zjednodušit
- adresy se komprimují pomocí dvou dvouteček za sebou - `::`
- kompresi lze v adrese použít jen jednou
- poté lze zpětně vyjádřit, kolik nul komprese obsahuje

#### Druhy vysílání
##### Unicast
- individuální adresa
- jedno konkrétní síťové zařízení

##### Multicast
- skupina adres
- více konkrétních zařízení, doručuje se všem

##### Anycast
- výběrové adresy
- více konkrétních zařízení, doručí se pouze jednomu (např. nejbližšímu)

#### Příklady adres
##### GUA
  - Global Unicast Address
  - globální, alternativa public adresy v IPv4
  - `2000::/3`

##### LLA
  - Link-Local Address
  - nejsou unikátní mimo síť, neměly by tedy být směrované routerem, pouze v lokánlí síti
  - `FE80::/10`

##### ULA
  - Unique Local Address
  - unikátní lokální
  - `FC00::/7`

##### Loopback
  - oproti IPv4 má pouze jednu Loopback adresu
  - směruje na samotný stroj, pro testování software
  - `::1/128`

##### Nespecifikovaná
  - nedefinovaná adresa IPv6
  - `::/128`

##### Multicast
  - doručen skupině zařízení, začíná **FF**
  - `FF0::/`

#### Zóna
- adresy ve své zóně musí být unikátní
- zóna má různé dosahy (Ethernet, podsíť, organizace, celosvětový)
- zóna má vždy nadřazenou zónu většího dosahu
- zóny stejného dosahu se nesmí překrývat
- ZoneID = identifikátor dané zóny

#### ICMPv6
- víceúčelový protokol
- pro ohlašování chyb při přenosu packetů
- vyhledává uzly
- přenáší informace pro odesílání multicastů
- uvnitř IPv6 datagramu

#### NDP
- Neighbor Discovery Protocol
- automatická konfigurace adres uzlů
- objev jiných uzlů na lince
- hledání dostupných routerů a DNS serverů
- obsahuje 5 typů packetů ICMPv6:
  - **RS (Router Solicitation)**
    - multicast žádost, snaží se nalézt routery
  - **RA (Router Advertisment)**
    - router ohlašuje přítomnost, může být rekace na RS
  - **NS (Neighbor Solicitation)**
    - k určení adresy souseda nebo ověření, že je soused stále dosažitelný
    - zjištění MAC adresy cíle
  - **NA (Neighbor Advertisment)**
    - reakce na NS žádost
  - **Redirect**
    - routery informují, že existuje lepší cesta k cíli (kratší)
