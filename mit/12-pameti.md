## 12 - Paměti
----

#### Paměti
- umožňují uchovávat informace, které lze zpětně získat
- **základní parametry:**
  - časování (zpoždění mezi operacemi)
  - frakvence (takt paměti, zvyšuje výkon)
  - kapacita (objem dat, se kterými může paměť pracovat)

#### Dělení pamětí
##### Nevolatilní
- nepotřebuje napájení pro uchování informací
- po odpojení napájení data zůstanou
- **př.:** HDD, SSD

##### Volatilní
- vyžaduje napájení k zachování dat
- při odpojení napájení se data ztratí
- paměť je rychlejší
- **př.:** RAM

#### Typy pamětí
##### ROM
- Read Only Memory
- **nevolatilní**
- obsah je dán při výrobě a nelze ho měnit (pouze pro čtení)
- v dnešních PC už se nenajde
  - dříve v nich byl uložen BIOS

###### PROM
- Programmable Read Only Memory
- nemají data z výroby
- data do paměti lze zapsat právě jednou

###### EPROM
- Erasable Programmable Read Only Memory
- stejné jako paměti PROM
- navíc dokáží data smazat pomocí UV zařízení

###### EEPROM
- Eletrically Erasable Programmable Read Only Memory
- místo UV zařízení lze data smazat pomocí napětí (na Erase pinu)

##### RAM
- Random Access Memory
- **volatilní**
- elektronicky přepisovatelná
- téměř okamžitý přístup k datům
- operační paměť v PC
- téměř neomezený počet přepisů

###### SRAM
- Static Random Access Memory
- každá paměťová buňka obsahuje několik tranzistorů, které uchovávají data
- paměť je rychlá, ale drahá
- používá se v CPU cache

###### DRAM
- Dynamic Random Access Memory
- každá paměťová buňka obsahuje tranzistor a kondenzátor
- pro uchovávání dat je nutno periodicky obnovovat paměť a data znovu zapisovat
- paměť je pomalá, ale levná

###### SDRAM
- Synchronous Dynamic Random Access Memory
- veškeré operace se odehrávají sychronně s hodinami z procesoru
- snižuje se čekací doba CPU
- zvyšuje se výkon
- reaguje na náběžnou hranu

#### DDR
- Double Data Rate
- typ paměti, co reaguje jak na náběžnou, tak sestupnou hranu
- několik verzí - DDR2, DDR3, DDR4
  - zpětně nejsou kompatibilní

#### HBM
- High Bandwidth Memory
- nový druh 3D pamětí
- vysokovýkonostní
- čípy se skádají na sebe místo vedle sebe
- velmi drahé na výrobu, v budoucnu mají nahradit DDR4 paměti i cache CPU

#### Cache
- paměť, která je velmi rychlá a má nízkou kapacitu
- používá se pro rychlý přístup k nejnutnějším datům daného zažízení
- většínou se používá pro opětovný přístup k datům
- v procesoru:
  - L1, L2, L3
    - čím větší číslo, tím pomalejší, ale větší paměť
