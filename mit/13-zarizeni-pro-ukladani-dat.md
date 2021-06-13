## 13 - Zařízení pro ukládání dat
----

### Pevné disky
#### HDD
- Hard Disk Drive
- elektromechanické zařízení pro zápis/čtení dat
- **nevolatilní**
  - nepotřebuje napájení pro uchování dat
- přistupuje k datům pomaleji než SSD / RAM
  - za cenu rychlosti poskytuje velké množství úložného prostoru
- maximální velikost se stále zvyšuje, jedná se o desítky TB
- obsahuje vyrovnávací paměť (cache)
  - pro dočasné ukládání informací

##### Princip
- v HDD se točí několik vrstev kotoučů s magnetickou vrstvou
- řadič řídí elektromagnetické hlavy
- elektromagnetické hlavy mění magnetickou orientaci částic na kotoučích
- vše je v héliu, aby nedošlo k mechanickému poškození

##### Parametry
- kapacita
- přístupová doba
- rychlost otáčení (RPM)
- přenosová rychlost
- rozhraní (SATA/ATA/PATA)
- kapacita cache

##### Výhody a nevýhody
- dobrý poměr cena / kapacita
- riziko mechanického poškození disku
- váha
- nízká rychlost
- **HDD se hodí pro ukládání velkého množství dat, které nepotřebujeme rychle načítat (filmy, hudba)**

##### Způsoby zápisu dat
- **HAMR**
  - Heat-Assisted Magnetic Recording
  - dočasné zahřátí plotny během zápisu
- **MAMR**
  - Microwave-Assisted Magnetic Recording
  - předávání energie pomocí mikrovlnného oscilátoru
- **SMR**
  - Shingled Magnetic Recording
  - rozdělení čtecích a zapisovacích hlaviček na více nezávislých

##### Rozhraní
- **SATA**
  - Serial Advanced Technology Attachment
  - sériová, obousměrná
  - standard dnešní doby
- **PATA**
  - Parallel Advanced Technology Attachment
  - též nazývána IDE
  - paralelní


#### SSD
- Solid State Drive
- polovodičový disk
- neobsahuje mechanické komponenty, ale integrované obvody
- data jsou v podobě elektrických nábojů na flash paměti
- každé SSD obsahuje Controller, který zajišťuje spojení mezi SSD pamětí a počítačem
  - obsahuje **FTL**
    - Flash Translation Layer
    - převod implementace paměti na logický blok
    - umožňuje s SSD pracovat stejně jako s HDD

##### Princip
- flash paměť ukládá data do polí paměťových buňek
- zastupují je tranzistory:
  - **SLC**
    - Single Level Cell
    - 1 stav na buňku
  - **MLC**
    - Multi Level Cell
    - 2 stavy na buňku
  - **TLC**
    - Triple Level Cell
    - 3 stavy na buňku
  - **QLC**
    - Quad Level Cell
    - 4 stavy na buňku
  - **PLC**
    - Penta Level Cell
    - 5 stavů na buňku
  - čím více buňka obsahuje stavů, tím je pomalejší a levnější

##### Výhody a nevýhody
- oproti HDD značně rychlejší
- horší poměr cena / kapacita
- méně hlučné, menší
- méně náchylné na mechanické poškození
- **SSD se hodí pro ukládání menšího množství dat, které je potřeba rychle načítat (OS)**

##### Rozhraní
- **SATA**
  - Serial Advanced Technology Attachment
  - sériová, obousměrná
  - standard dnešní doby
- **PCI-e NVM-e**
  - Peripheral Component Interconnect Express Non Volatile Memory Express

##### TRIM
- příklad speciální operace na SSD
- při mazání souboru OS se mažou pouze metadata, obsah souboru zůstane
- u **HDD** je čtecí hlava kombinovaná s mazací hlavou -> toto nevadí
- u **SSD** je nutné před zápisem dat stará smazat -> operace je pomalá
- operace TRIM se obvykle provádí v čase, kdy se na SSD neočekává žádná další operace

---

### Optická média
- zapisují se digitální data optickou cestou
- data jsou uložena v prohlubních (pity)
- prohlubně odrážejí laserové světlo
- při **zápisu** se vypálí polykarbnoátová vrstva a tím se odhalí prohlubeň
- při **čtení** laser svítí na prohlubeň a určuje logické 1 a 0 podle toho, zda se světlo odrazí

#### CD
- Compact Disc
- kapacita 700MB
- existují verze pouze pro čtení, s jednorázovým zápisem a přepisovatelné

#### DVD
- Digital Video Disc
- kapacita 4.7GB
- ukládání dat do dvou vrstev
- lepší korekce chyb, jiný souborový systém
- existují verze pouze pro čtení, s jednorázovým zápisem a přepisovatelné

#### Blu-Ray
- nejmodernější disk
- využívá modrý laser
- kapacita 50GB
- existují verze pouze pro čtení, s jednorázovým zápisem a přepisovatelné

---

### Rozhraní

#### PATA
- Parallel Advanced Technology Attachment
- **paralelní**
- dříve označováno jako ATA / IDE
- nejvyšší rychlost - 133MB/s

#### SATA
- Serial Advanced Technology Attachment
- **sériové**
- rychlejší než PATA, dnes standard
- několik verzí, odděluje je rychlost
- není nutnost rozlišovat Master/Slave
- podporuje Plug & Play
- nejvyšší rychlost - 600MB/s

#### SCSI
- Small Computer System Interface
- **paralelní**
- zastaralé, dříve používáno na některých serverech
- největší rychlost - 40MB/s

#### SAS
- Serial Attached Small Computer System Interface
- **sériové**
- náhrada za SCSI pro servery
- kompatibilní se SATA
- největší rychlost - 1200MB/s

#### Souhrn
- u PC i u serverů se dříve používaly paralelní rozhraní (PATA, SCSI)
- postupem času se nahradily za sériové (SATA, SAS)
- důvodem pro to je rychlost, zjednodušení komunikace (kabel, master/slave) a nové funkce (plug&play)
