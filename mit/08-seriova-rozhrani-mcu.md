## 08 - Sériová rozhraní mcu
----

#### Parametry sběrnic
- vzdálenost
- komunikační rychlost
- počet zařízení, které mohou komunikovat
- druh komunikace
  - Point-to-Point
    - UART
  - single-master
    - SPI/Microwire, RS422, 1Wire
  - multi-master
    - někdy RS485, I2C, CAN
- arbitrace u multi-master (když vysílá více zařízení naráz)
- adresace (hardwarově / softwarově / vůbec)
- zabezpečení (kontrola správnosti přenesených dat)
- odolnost proti rušení

#### Popis sběrnic
##### U(S)ART
- Universal (Synchronous) Asynchronous Receiver Transmitter
- **point-to-point**
- přes nástupem USB se používal pro seriové porty PC
- dokáže konvertovat data mezi seriovým a paralelním portem
  - pomocí posuvných registrů
- obsahuje softwarově řízené obvody pro řízení externích modemů
- vyrovnávací paměť typu FIFO
  - First In First Out (fronta)
- není odolný proti rušení

##### I2C (I^2C)
- Inter Integrated Circuit
- **multi-master**
- pokud začnou dvě zařízení komunikovat nastejno, přednost má to, které zapisuje více nul
  - řešení arbitráže
- zařízení detekuje, že je sběrnice zaneprázdněná
  - čeká na její uvolnění
- 7bit široká sběrnice, celkem 128I2C adres
  - některé jsou ovšem rezervované
- používá se pro připojení periferií
  - senzory teploty, AD převodníky
- není odolný proti rušení

##### 1Wire
- **single-master**
- pro komunikaci dvou zařízení s nízkou datovou rychlostí a napájení
- podobná jako I2C, má nižší datovou propustnost a vyšší dosah
- používá se u malých a levných zařízení (termometry, časovače, senzory napětí)
- umožňuje zapojit zařízení na jednu sběrnici, která je ovládaná jedním masterem
- není odolný proti rušení
- může sloužit zároveň pro napájení
  - přes diodu a kondenzátor
- je možné připojovat zařízení dynamicky
  - binární vyhledávací strom

#### Popis sériového portu ATmega64
- **UART**
  - Univeral Asynchronous Receiver Transmitter
  - obě strany si samy generují hodiny
- **USART**
  - Univeral Synchronous Asynchronous Receiver Transmitter
  - navíc přidán synchronní mód
    - vodič navíc, který funguje jako synchronizace mezi stranami
    - hodiny generuje pouze jedna strana
      - master-slave
- dole - konfigurační registry, nepodstatné
- nahoře - generování přenosové rychlosti
  - obousměrná komunikace (napravo)
- uprostřed je vysílač, nepodstatné
- dole je přijímač
  - obsahuje **clock recovery** a **data recovery**
    - během bitového intervalu se vstup čte opakovaně
      - častější hodnota je prohlášena za správnou
  - obsahuje **UDR**
    - rozdělen na vstupní (reciever část) a výstupní (transmitter část)
      - vstupní část funguje jako FIFO
        - First In First Out (fronta)
        - zajišťuje to, aby procesor měl více času na zpracování dat
        - pokud je fronta plná a přijdou data, které se do ní nevejdou, jsou zahozeny
