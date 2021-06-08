## 11 - Síťové prvky, přiřazení k vrstvám OSI/ISO
----

#### Repeater (opakovač):
- **fyzická vrstva** (L1)
- příjímá zkreslený / poškozený signál, opraví ho a posílá dál
- neumí data nijak filtrovat
- posílá data broadcastem dál
- příklad - WiFi extender
  - zvyšuje dosah WiFi sítě, ovšem klesá její rychlost

#### Hub (rozbočovač):
- **fyzická vrstva** (L1)
- všechna data, která přijdou na nějaký port, zkopíruje na všechny ostatní porty
- vysílá broadcast
- velmi jednoduchý
- má zároveň i funkce repeateru (obnoví data)
- přetěžuje síť (prvky musí filtrovat pouze ty data, co jsou pro ně určené)

#### Bridge (most):
- **spojová vrstva** (L2)
- "switch, co má pouze dva porty"
- spojuje 2 části sítě
- není vidět pro protokoly vyšších vrstev
- sestaví si tabulku s porty MAC adres z obou částí sítě
- když přijde packet, podle cílové adresy ho buď pošle na druhou stranu, nebo vyřadí
  - snižuje se provoz v síti, pokud se posílají packety přes broadcast všem
- když není adresa v tabulce, pošle packet broadcastem

#### Access point (přístupový bod)
- **spojová vrstva** (L2)
- zkratka AP
- poskytuje klientům vstup do sítě
- typicky připojení přes Wi-Fi

#### NIC (síťová karta)
- **spojová vrstva** (L2)
- Network Interface Controller
- možnost, aby počítač komunikoval v rámci sítě
- buď integrované na základní desce, nebo dedikovaná (PCI / PCI-e)
- každá síťová karta má svou unikátní MAC adresu

#### Switch (přepínač):
- **spojová vrstva** (L2)
- "chytřejší hub"
- analyzuje packety a posílá je na port, kam přísluší
- pokud switch neví, pošle broadcast na všechny porty
  - poté dostane odpověď, který port byl ten správný
  - postupně se učí, které porty mají jaké MAC adresy
- tyto informace ukládá do CAM tabulky

#### Router (směrovač):
- **síťová vrstva** (L3)
- spojuje více sítí dohromady
- používá routovací tabulku a hledá nejlepší cestu packetu
- v lokální sítí je router gateway
- pokud router neví, kam packet odeslat, zahodí ho

#### Firewall:
- **transportní vrstva** (L4)
- řídí a zabezpečuje provoz mezi sítěmi
- brána, která rozhoduje, zda spolu dvě sítě navážou spojení
- kontroluje zabezpečení, stav spojení, protokoly apod.

#### Nastavení routeru a switche pomocí managementu
- switch se dá managovat vytvoření virtuálních LAN (VLAN)
  - na jednom zažázení se vnitřně vytvoří další, které se chovají jako samostatné sítě
- pro komunikaci mezi VLAN se používá Router On A Stick
- pro propojení fyzického switche s VLAN se používá trunk

#### Domácí router a firemní router
- **domácí router**
  - obsahuje jeden WAN port pro přístup k internetu
  - dále obsahuje několik LAN portů pro přídavné zařízení
    - PC, telefony, tiskárny
  - obsahuje anténu pro bezdrátové připojení
    - není potřeba Access Point
- **firemní router**
  - větší možnost řízení
  - odděluje různé sítě
  - zaručí oddělení logických částí
    - např. server, tiskárna atd.
  - omezuje práva přístupu
