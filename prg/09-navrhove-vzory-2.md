## 09 - Návrhové vzory II.
----
NV II. - strukturalni

#### Proxy - zástupce

- nahrazuje přístup k zastupované hodnotě
- v případě, že daná hodnota má nějaké omezení přístupu
- implementuje se pomocí rozhraní / abstraktní třídy
- příklad - bankovní šek

#### Command - příkaz

- mění funkce na objekty, s nimiž se poté dá pracovat
- má připravené metody a uživatel do nich musí dodat parametry
- příkazů lze vytvářet více vedle sebe
- příklad - objednávka v restauraci

#### Iterator

- zprostředkovává přístup k objektům v kolekci
- implementace jeho struktury je skrytá
- může se použít buď externí, nebo interní
- příklad - cykly (systematické procházení kolekcemi)

#### State

- používá se v případě, že mezi stavy objektu je velký rozdíl
- implementuje se objekt, který reprezentuje stav pomocí stavových tříd
- dělí se na stavově závislé a nezávislé části
- příklad - auto s automatickou převodovkou

#### Template metoda

- v případě, že chceme, aby podtřídy mohly upravovat kroky algoritmu
- některé její funkce definuje až příslušná podtřída
- abstraktní / virtuální metody
- příklad - denní rutina zaměstnance

#### Facade

- pro zjednodušení komunikace
- snižuje počet objektů nutných ke komunikaci
- používá se na centralizaci a snížení duplicity kódu
- příklad - zákaznická podpora

#### Adapter

- pro změnu rozhraní objektu
- vyžaduje kompletní implementaci rozhraní
- usnadňuje definici nových tříd a zabezpečí spolupráci existujících
- příklad - cestovní adaptér
