## 01 - Mikrokontroléry (mcu) - základní pojmy
----

#### Mikrokontrolér
- elektronický integrovaný obvod
- obsahuje:
  - řadič
    - **dekóduje** instrukce (instruction decoder)
  - ALU (arimeticko-logická jednotka)
  - paměť
  - porty
  - integrované periferie
- s okolím komunikují pomocí univerzálních obousměrných vodičů
- používá se v elektronických zařízení s digitálním řízení
  - např. PLC

#### Von Neumannova architektura
- neumožňuje zároveň číst instrukci a manipulovat s datovou sběrnicí
- nepočítá s více jádrovými procesory, najednou zvládá pouze jeden program
- jednoduchá, levnější
- pouze jedna sběrnice limituje počítač

#### Harvardská architektura
- má fyzicky oddělenou paměť pro program a pro instrukce
  - lze do obou pamětí přistupovat současně
- ATmega64 je Harvardská architektura
- obě paměti mohou mít odlišné technologie a velikost
  - např. flash paměť a SRAM
- větší náklady na výrobu (2x více sběrnic)

#### Vlastnosti Atmel AVR
- RISC architektura
- ATmega64 vs ATmega64**L**
  - **L = low power**
    - nižší spotřeba, poloviční max. frekvence
- 8bit
- **datová paměť** - 4Kb (SRAM)
- **rozšíření datové paměti, vnitřní uložiště** - 2Kb (EEPROM)
- 2 cyklová násobička
- integrované periferie
  - čítače, časovače
  - ADC
  - 3 sériové komunikace
- 53 vstupně výstupních pinů (I/O)
