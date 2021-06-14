## 13 - Směrování, směrovací tabulky, směrovací protokoly
----

#### Směrování
- L3 vrstva (síťová)
- v síti vidíme pouze zařízení, která se nachází ve stejné síti
- pro přesun z naší sítě do jiné potřebujeme router
  - router ovšem taky vidí pouze sítě, do kterých patří
- tento problém řeší **směrování**
  - data, která nemůžeme doručit přímo, doručíme někomu jinému:
    - tomu, kdo je bude moci doručit přímo **(last-hop)**
    - tomu, kdo je blíže k cíli **(mezilehlý router)**
    - tomu, kdo má větší šanci najít správnou cestu **(default-route)**
- **směrování = proces hledání nejlepší cesty pro data, která nelze doručit přímo přes síť**

#### Směrovací tabulka
- routing table
- v RAM paměti routeru
- udržuje informace, jak doručit data do neznámých sítí
- každý záznam obsahuje:
  - adresu cílové sítě + masku
  - gateway sítě
  - název odchozího rozhraní
  - IP adresu dalšího routeru
  - metrika (výhodnost cesty)
- jelikož se v tabulce můžou nacházet duplicity, router postupně hledá shodu s nejvýhodnější cestou

![Tabulka](https://ctrlv.cz/shots/2021/06/08/soYO.png)

#### Default route
- má nulovou masku (0.0.0.0/0)
- je nejméně specifická
- shoduje se se všemi adresami a vyhodnocuje se jako poslední
- IP datagram je pomocí default route předán nadřazenému routeru
  - pokud nadřazený router zná cestu, pošle tam datagram
    - pokud ne, předá datagram o úroveň výše dalšímu routeru

#### Metrika
- vypočítává kvalitu trasy
- čím méně, tím lépe
- počítá se podle různých parametrů:
  - počet hopů, cena, rychlost, stabilita, zatíženost

#### Směrovací protokoly
- záznamy se do směrovací tabulky přidávají buď ručně, nebo automaticky
- ručně přidané záznamy = **statické routy**
  - rychlé, bezpečné
  - nevhodné pro velké sítě
- automaticky přidané záznamy = **dynamické routy**
  - pomocí směrovacích protokolů
  - router se naučí cestu k sítím, které nezná
  - stačí nastavit pouze jednou a poté fungují samy
  - přizpůsobují se topologii sítě (při výpadku hledají alternativu)

#### Statické směrování vs dynamické směrování
- u **dynamického směrování** nemusí administrátor znát topologii sítě
- jakékoliv změny se okamžitě šíří díky směrovacím protokolům
- jednodušší administrace, protokol dělá část práce za admina
- u **statického směrování** lze na pevno nastavit cesty
  - větší bezpečnost
- je málo flexibilní a nemůže se dostatečně konfigurovat

#### Dynamické směrovací protokoly

##### RIP
- distance-vektor protokol
- Routing Information Protocol
- nejjednoduší protokol s jednoduchou konfigurací
- hloupá metrika
- první verze **(RIP)** posílal směrovací tabulky broadcastem, což zatěžovalo síť
- druhá verze **(RIPv2)** posílá směrovací tabulky multicastem, navíc umí pracovat s podsítěmi a maskami sítě (CIDR)
- nejnovější verze **(RIPng)** má podporu IPv6 a umožňuje provádět lepší autentizace

##### EIGRP
- hybridní protokol
- Enhanced Interior Gateway Routing Protocol
- pravidelně kontroluje, zda je trasa k dispozici
- místo směrovací tabulky posílá změny topologie
- podpora pro CIDR a proměnnou délku podsítí
  - Classless Inter-Domain Routing
  - maska je určena počtem bitů, nikoliv třídou IP adres
- MD5 autentizace

##### OSPF
- link-state protokol
- Open Shortest Path Find
- provádí změny v tabulce na základě změn v síti
- nejpoužívanější v samosprávých systémech
- routery kontrolují okolní routery
- je velmi paměťově náročný

##### BGP
- distance-vektor
- Border Gateway Protocol
- používají ho provideři (ISP)
- směrovací tabulky obsahují stovky tisíc záznamů
- vyměňují se pouze informace o změnách, nikoliv celé tabulky

#### Link-state protokoly
- pro správu sítě v rámci jedné domény (např. firma)
- router zjišťuje, zda má v síti další routery a testuje jejich dostupnost
- poté routery informuje o jejich sousedech
  - každý router ví o všech ostatních
- takto zmapuje celou síť
- podle toho pro packet určuje nejlepší cestu
- pro rozlehlejší sítě nutno rozdělit na části kvůli zatěžování sítě

#### Distance-vector protokoly
- routery neznají strukturu sítě, pouze své nejbližší sousedy
- vyměňují si kompletní kopii směrovacích tabulek
- routery periodicky vysílají a díky grafovému algoritmu vypočítají vzdálenost do ostatních uzlů
- vzniká riziko zacyklení
