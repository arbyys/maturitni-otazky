## 05 - Čítačové podsystémy mcu
----

#### Režím čítače / časovače
- čítač / časovač = **registr**
- obsah lze číst i zapisovat
- obsahuje řídící vstupy
   - **count** - inkrementace
   - **clear** - vymazání obsahu
   - **direction** - nepovinný, pokud je čítač up/down, určuje jeho směr
- využití čítače/časovače
  - časové spoždění po startu oscilátoru
  - časové spoždění po zapnutí mcu

##### Čítač vs časovač
- **Čítač**
  - připojen na externí pin
    - hodinový signál **nemusí** být periodický
- **Časovač**
  - přes předdělič připojen na frekvenci instrukčního cyklu
    - hodinový signál **je** periodický se známou frekvencí

#### Popis pro ATmega64
- *nahoře* čítač/časovač
- řídící logika čítače/časovače
- výběr cyklu
  - externí
  - frekvence instrukčního cyklu
- další části (*uprostřed*) pouze vylepšují vlastnosti čítače/časovače - rozšířené funkce
- *dole* řídící registry

##### Rozšířené funkce
- **Compare**
  - časovač doplněn komparátorem a porovnávacím registrem
    - když se shoduje porovnávací registr a časovač, lze generovat daný signál na výstupním pinu
      - náběžná hrana / sestupná hrana / negace hodnoty
  - u ATmega64 jsou 3 komparátory
  - **Hardwarové zkracování rozsahu**
    - compare v případě určité hodnoty vyšle signál na pin "TOP"
      - to vynuluje čítač
    - výhodnější než softwarové
- **Capture**
  - obrácená funkce než compare
  - pro zjištění **přesného** času určité události
    - obsah časovače se uloží do záchytného registru když přijde vstup
      - lze k němu poté zpětně přistupovat
  - pokud bychom to řešili softwarově, může dojít ke spoždění
    - režim capture je ideální řešení, protože je hardwarově
- **PWM**
  - režim compare, kde lze nastavit délku periody a šířky pulzu
  - u ATmega64 je nutno použít časti Compare a Capture

##### Dohlížecí časovač
- watchdog timer
- časovač, který má nezávislý vstup hodinového signálu
  - když přeteče, mcu se resetuje
- uvádí se, co bylo důvodem restartu
  - mcu na to může reagovat
- slouží jako ochrana před chybami
