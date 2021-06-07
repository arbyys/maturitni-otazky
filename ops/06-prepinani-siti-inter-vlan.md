## 06 - Přepínání sítí, Inter-VLAN
----

#### Propojení VLAN
- Inter-VLAN se používa pro směrování packetů mezi VLAN
- základní architektury Inter-VLAN:
  - Router-on-a-stick
  - Router-on-a-stick pomocí trunků
  - Layer 3 switch

#### Router-on-a-stick

##### Klasický
- základní, nejjednodušší metoda Inter-VLAN
- router se připojí ke všem VLAN pomocí jednoho zařízení (většiou switch)
  - příslušné packety posílá do VLAN podsítí
- router má fyzické rozhraní Ethernet pro každou VLAN
- funkce L2 vrstvy a L3 vrstvy jsou fyzicky odděleny
- nevýhodou je nízká rychlost, Router-on-a-stick je vhodný především pro menší sítě
  - **protože router je stavěn na bázi softwaru**, zatímco switch na bázi hardwaru

##### Pomocí trunků
- díky použitím trunků se zvyšuje počet rozhraní pro VLAN
  - Router-on-a-stick pomocí trunků se dá použít i pro větší sítě
- používá tagování packetů (např. pomocí 802.1Q)
- nevýhodou je stále nízká rychlost, v podstatě totožná s Router-on-a-stick

##### Konfigurace
1. Switch - vytvoření VLAN
2. Switch - přepnutí portů do access-mode
3. Switch - přiřazení VLAN jednotlivým rozhraním
3. Switch - **přepnutí portů do trunk-mode (kvůli komunikaci s routerem)**
4. Router - **nastavení sub-interface pro jednotlivé VLAN**
4. Router - **zapouzdření pomocí standardu 802.1Q**
4. Router - nastavení výchozí brány

#### L3 switch
- Layer 3 switch
- nejlepší řešení
- obyčejný switch, který navíc umí směrovat jako router
- lze nastavit, že se některé porty budou chovat jako porty z routeru (místo jako ze switche)
- směrování je velmi rychlé, protože je **realizováno hardwarově**
- omezený počet záznamů ve směrovací tabulce L3 switche (16/32/64)

##### Konfigurace
- použití SVI
1. Switch - vytvoření VLAN
2. Switch - přepnutí portů do access-mode
3. Switch - přiřazení VLAN jednotlivým rozhraním
4. Router - **vytvoření virtuálních rozhraní pro VLAN**
5. Router - nastavení výchozí brány pro danou VLAN
6. Router - povolit směrování

#### Legacy Inter-VLAN routing
- nejstarší řešení přepínání sítí
- použití routeru s více interface
  - každé interface má vlastní VLAN
- switch s access-mode porty, který posílá data na příslušnou VLAN

##### Konfigurace
1. Switch - vytvoření VLAN
2. Switch - přepnutí portů do access-mode
3. Switch - přiřazení VLAN jednotlivým rozhraním
4. Router - nastavení výchozí brány na VLAN rozhraní
