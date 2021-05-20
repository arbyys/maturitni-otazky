## 14 - Normalizace databáze
----

- stupně ideální databáze
- každým stupněm normalizace se přibližujeme více "ideální databázi"
- více tím zatěžujeme databázový stroj = pomalejší dotazy
  - za cenu tohoto dostaneme menší šanci porušení integrity dat
- snažíme se tyto dvě hodnoty vyrovnat
  - dosáhnout co největší stupeň normalizace za co nejmenší snížení rychlosti

#### OLAP

- Online Analytical Processing
- pro uspořádání velkých objemů dat tak, aby dávala smysl uživatelům, co se zabývají analýzou obchodních trendů
- důležitá je rychlost
- zisk souhrnných dat

#### OLTP

- Online Transaction Processing
- umožňuje co nejsnadnější a nejbezpečnější modifikaci dat v prostřední s mnoha uživateli
- důležitá je integrita (soudržnost)
- uložení a organizování nových dat

#### Normální formy

- pro splnění každé formy musí být tabulka ve všech předchozích formách
- Nenormalizovaná tabulka
- NF 0
- NF 1
- NF 2
- NF 3
- další...

#### 0. NF

- tabulka obsahuje alespoň jedno pole, které obsahuje více než jednu hodnotu
- (jednoduché splnit)

#### 1. NF

- v tabulce jde do každého pole dosadit pouze jedna hodnota (data jsou atomická, nejdou dále dělit)

![1. NF](https://ctrlv.cz/shots/2021/05/20/hXan.png)

#### 2. NF

- neklíčové atributy musí být závislé na celém klíči (na všech primárních klíčích)
- závisí pouze u tabulek s více primárními klíči

![2. NF](https://ctrlv.cz/shots/2021/05/20/aeQI.png)

#### 3. NF

- žádný neklíčový atribut není transitivně závislý na žádném klíči schématu
  - neexistuje "nepřímá" závislost mezi sloupci
- hodnoty v jednotlivých sloupcích spolu nesmí souviset
  - pokud souvisí, oddělí se ve vedlejší tabulce

![3. NF](https://ctrlv.cz/shots/2021/05/20/3r8L.png)
