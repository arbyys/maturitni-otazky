## 04 - Připojování externích periferií k mcu
----

schéma PVK40
#### Tlačítka
- nejzákladnější způsob připojení
- tlačítka mají nad sebou pull-up odpory
  - pull-up odpor definuje logickou úroveň pokud **není** tlačítko stisknuto (1)
  - zároveň omezuje množství proudu když tlačítko **je** stisktnuto (0)
- tlačítka jsou propojeny do mikrokontroleru
  - jeden konec vede na **zem**
  - druhý **přes pull-up odpor do kladného napětí**

##### Výhody a nevýhody
- jsou zapojeny jednodušše
- snadná detekce
- hodně obsazených I/O pinů
  - ostatní možnosti zapojení snižují počet I/O pinů

##### Další varianty zapojení
- **přes multiplexor**
  - z více vstupů vybírá jeden konkrétní podle adresy
- s **posuvným registrem**
  - vloží se do něj všechna data najednou, poté se postupně čtou

#### Klávesnice
- přes **maticové zapojení**
- polovina pinů jsou vstupy (s pull-up odpory) a druhá polovina výstupy
  - dělení tlačítek na skupiny, spodní piny "aktivují" jednotlivé skupiny tlačítek
- pull-up odpor zapíše 1, my zapíšeme na skupinu tlačítek 0, díky tomu lze poznat, jaké tlačítko je stisknuté

#### 7-segmentový displej
- na schématu:
  - čtyřmístný (4 znaky)
  - všechny zapojeny **přes společnou sběrnici**
    - **postupně se displejům spíná napájení**, díky tomu lze zapsat 4 různé hodnoty
      - hodnoty se zapisují postupně ve velmi velké rychlosti na všechny displeje

##### Další varianty zapojení
- každý displej má **samostatný vstup**
  - jednoduché, ovšem plýtvá se s počtem pinů
- přes posuvný registr
- přes společnou sběrnici a navíc přidaný registr ke každému displeji
  - pamatuje si hodnotu, nemusíme ji měnit z mcu

#### LED
- LED **přímo připojeny na PIN** s odporem, druhá část na zem
  - LED poté svítí, když se na pin zapíše 1
- výpočet odporu:
  - (celkové napětí minus úbytek na diodě) děleno (proud)
  - `(U[celk] - U[LED]) / (I[LED])`

##### Další varianty zapojení
- **s tranzistorem který funguje jako spínač**
- unipolární / bipolární
- menší proudové zatížení mcu
- ve schéma použit u bargrafu
  - bargraf = integrovaná kaskáda LED

#### Inteligentní displeje
- **alfranumerický displej**
  - umí zobrazit pouze písmena a číslice
  - pracují s vnitřní ASCII tabulkou
- **grafický displej**
  - umí pracovat s jednotlivými pixely
  - lze zobrazovat i různé grafické prvky

#### Shrnutí
- **jde o počet I/O pinů, které použijeme na připojení dané periferie**
- **jde o způsob komunikace s danou periferií**
