## 15 - DHCP, NAT, DNS
----

#### DHCP
- Dynamic Host Configuration Protocol
- automatická konfigurace počítačů v síti
- přiřazuje IP adresu, masku, bránu a DNS adresu z daného DHCP poolu
- tyto údaje se nemusí nastavovat staticky

##### Princip činnosti
1. klient a server spolu komunikují na portech 67 a 68
2. klient, který chce adresu, vyšle broadcastem `DHCPDISCOVER`
3. DHCP server odpoví packetem `DHCPOFFER` s nabídkou adres
4. klient si vybere adresu a pošle serveru packet `DHCPREQUEST`
5. server odpoví packetem `DHCPPACK` (acknowledge) a potvrzuje přiřazení
6. klient má přiřazenou adresu a veškeré potřebné údaje

##### Relay agent
- pokud se nachází DHCP server na jiné síti, která je od aktuální dělena routerem, použije se **Relay agent**
- nachází se na routeru
- přeposílá dotazy DHCP serveru
- navíc se ještě přidává číslo sítě a maska sítě, aby dokázal DHCP server vygenerovat správnou adresu

##### Možnosti přidělování adres
- **Statická alokace**
  - na pevno nastavená adresa klientovi podle MAC adresy, DHCP server ji pouze oznámí
  - používá se tam, kde by změna adres ohrozila chod služeb
- **Automatická alokace**
  - klientovi přiřadí stálou adresu
  - používá se při stálých zařízeních, kde změna adres neohrozí funkci ostatních služeb
- **Dynamická alokace**
  - přiřadí klientovi adresu pouze na určitý čas
  - používá se při připojení do sítě pouze na určitou dobu

#### Automatické přiřazování adres v IPv6
##### SLAAC
- Stateless Address Autoconfiguration
- bezstavová autokonfigurace adres
- implementováno na routeru
- host vyšle multicast žádost `Router Solicitation`
- router mu odpoví pomocí `Router Advertisement` s konfiguračními parametry
- pokud tuto konfiguraci nelze použít, lze požádat DHCPv6

##### DHCPv6
- stavová autokonfigurace adres
- na rozdíl od SLAAC vyžaduje svůj speciální server
- navíc má **zprostředkovatele**, který předává DHCP zprávy mezi klientem a serverem, pokud nejsou ve stejné podsíti
  - "relay agent"
- podobně jako v IPv4 má 4 kroky přiřazení adres:
  - discover
  - offer
  - request
  - acknowledge

#### NAT
- Network Address Translation
- proces výměny adresy v IP hlavičce za jinou
- jejím smyslem je překlad neveřejných adres v lokálním síti na unikátní veřejné adresy
- šetří adresní prostor
  - umožňuje schovat celou síť za jednu jedinečnou veřejnou adresu
  - připojí se více počítačů

#### Port forwarding
- přesměrování portů z jednoho uzlu na jiný
- použito společně s NAT
- umožní vzdáleným uzlům se připojit ke specifickému uzlu v privátní LAN síti
- např. směrování portu 21 k umožnění FTP přístupu uvnitř privátní LAN z internetu

#### NAT64
- implementace NAT v IPv6
- usnadňuje přechod z IPv4 na IPv6
- umožňuje komunikaci dvou zařízení, kde každé podporuje odlišnou verzi IP protokolu
- zajišťuje přístup k IPv4 internetu pro stroje s adresou IPv6
  - druhým směrem lze komunikovat pouze velmi omezeně

#### DNS
- Domain Name System
- hierarchický systém, celé DNS je velký strom
- přiřazuje IP adrese snadno zapamatovatelné symbolické jméno
- prohlížeč dané jméno zpracuje pomocí DNS a nahradí ho za adresu
- učel DNS je vyloučit nutnost si pamatovat adresy
