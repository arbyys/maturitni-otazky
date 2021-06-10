## 14 - Grafické karty
----

#### Grafická karta
- jedna ze základních komponent počítače
- zajišťuje grafický výstup na zobrazovací jednotku
- může být:
  - integrovaná (v CPU), využívá operační paměť počítače
  - dedikovaná, má vlastní videopaměť
- převádí data z procesoru na videosignál
- stará se o většinu výpočtů, i negrafických

##### Struktura

- **GPU**
  - Graphics Processing Unit
  - grafický čip
  - stará se o výpočty a vykreslování dat
- **paměť**
  - ukládání dat používaných pro výpočty
- **DAC**
  - Digital Analog Converter
  - převodník, který převádí analogová data na digitální signál
- jako systémová sběrnice se většinou používá **PCI / PCI-e**
  - Peripheral Component Interconnect (Express)

##### Funkce
- data z počítače se uloží do paměti
- z paměti se postupně data dostávají do GPU
- po vypočítání pozic, pohybů a všech ostatních výpočtů se vytvoří obraz
- výsledný obraz je digitálně analogovým převodníkem převeden na digitální signál
- výsledek je poslán na monitor

##### Parametry
- velikost grafické paměti
- typ grafického čipu
- obnovovací frekvence jádra
- spotřeba
- výkon

#### Akcelerace
- využití grafické karty pro určité vektorové výpočty
- tyto výpočty místo procesoru řeší grafická karta rychleji a efektivněji
- stíny, světelné efekty

#### GPU vs CPU
- GPU má více ALu jednotek a jader
- CPU má větší cache

![Rozdíl GPU vs CPU](https://ctrlv.cz/shots/2021/06/09/vLpa.png)

#### Vytvoření 3D scény
- nejdříve je nutno vytvřit 3D modely
  - většinou tvořeny pomocí polygonů
  - výsledkem je objekt tvořen až tisícem geometrických ploch
    - snažíme se použít co nejméně polygonů a dosáhnout co nejlepšího výsledku
- na tyto polygony jsou naneseny textury a shadery (stíny)
- textury jsou oproti modelu 2D a nanesou se na něj
- všechny objekty mají ve scéně své souřadnice
  - mohou se pohybovat do všech směrů
- důležitá součást je **rendering**, aneb tvorba obrazu na základě počítačového modelu
  - exportování reálného obrazu
- aplikace běží v nekonečné smyčce
  - v případě zjištění uživatelského vstupu, celá scéna se překreslí znovu

#### Využití GPU pro negrafické výpočty
- **GPGPU**
  - General Purpose computing on Graphics Processing Unit
- GPU má větší výkon než CPU
- na GPU se využívá paralelizace k výpočtu jednoduchých algoritmů
- CPU se naopak používá pro složitější algoritmy, protože je univerzálnější
- DirectX, OpenGL
