## 03 - Paralelní porty mcu
----

#### Popis portů ATmega64
- (v dokumentaci první stránka - *I/O and Packages*)
- **ATmega64 - 53 programovatelných vstupů/výstupů**
- porty od A do G
  - A - F jsou 8bit
  - G jsou 5bit
- **všechny porty jsou obousměrné (nikoliv současně) a digitální**
  - digitální = lze zapisovat a číst 0 nebo 1
  - obousměrné = lze používat buď ve vstupním nebo výstupním režimu a tento režim nastavovat
- porty jsou po resetu ve vstupním režimu (je na nich 0)
  - **velký vstupní odpor - působí proti nežádoucím jevům**
- některé porty lze přepnout do analogového režimu
  - poté slouží jako vstup pro AD převodník
- některé porty mají alternativní funkce pro připojení integrovaných periferií
  - externí paměťová sběrnice, alternativní vstup pro AD převodník

#### Obvodový popis portu
![Obrázek](https://ctrlv.cz/shots/2021/06/10/vVYh.png)
- obrázek str. 67
- šipky co vedou **z datové sběrnice** reprezentují výstupní větev
- šipky co vedou **do datové sběrnice** reprezentují vstupní větev

##### Výstupní větev
- klopný obvod typu D - **PORT**
  - zapisuje data na výstup
- klopný obvod typu D - **Data Direction (DD)**
  - ovládá oddělovač pod ním
- **prodový budič + oddělovač** uprostřed
  - lze ho zavřít přivedením nuly z vrchu
  - po resetu je ve vstupním režimu (zavřený)

##### Vstupní větev
- vlevo nahoře - **softwarový pull-up odpor**
  - definuje logickou úroveň pokud není tlačítko stisknuto (1)
- vlevo dole - **analogový oddělovač**
  - funguje stejně jako oddělovač ve výstupní větvi, ale i pro analogové hodnoty
- za ním - **schmittův klopný obvod**
  - regeneruje náběznou a sestupnou hranu
    - rekonstrukce zdeformovaného signálu
  - v kombinaci s externím kondenzátorem funguje jako filtrace zákmitů (šumu)
- synchronizer - **zablokuje změnu vstupního signálu než se zapíše**
  - sledovač a hranový klopný obvod

#### Elektrické vlastnosti
- krákodobá výdrž - **40mA**
- dlouhodobá výdrž:
  - při napětí 3V - **10mA**
  - při napětí 5V - **20mA**
- piny naráz nesmí procházet více než **400mA**
- pro některé piny je definovaný součtový limit
- **logická 0** je od 0 do 0.2V
- zakázané pásmo je od 0.2 do 0.6V
- **logická 1** je od 0.6V výše
- každé zatížení má definováno maximální výstupní napětí

#### Příklady instrukcí pro prácy s porty
- ATmega64 je load-store architektura
  - většina instrukcí může pracovat pouze z registry, ovšem jsou i výjimky
- v názvu instrukce je **port** nebo **I/O register**
- `IN`, `OUT`
- `SBI`, `CBI`
- `SBIC`, `SBIS`
- lze hodnotu na bity zapsat / přečíst
- lze nastavit bit / vynulovat / otestovat jeho logickou úroveň
