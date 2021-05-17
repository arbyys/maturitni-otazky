## 05 - Objektové programování I.
----

#### Strukturované vs. objektové programování
##### Strukturované
- skoky
- použití funkcí
- vše v jednou souboru

##### Objektové
- použití objektů a tříd
- většinou ve více souborech

#### Třída

- vzor, podle kterého se vytváří objekty
- vytvořené objekty se nazývají instance
- třída určuje, jaká se v objektu nacházejí data
- příklad - student

#### Objekt

- je instancí třídy
- z jedné třídy se vytvoří několik objektů
- více objektů se stejnou třídou se liší svými atributy (daty)
- příklad - Jan, Ondřej

#### Základní objektové vlastnosti

##### 1. Zapouzdření

- umožňuje skrýt určité funkce nebo atributy tak, aby byly přístupné pouze uvnitř objektu
  - typicky modifikátory přístupu **private, protected**
- eliminuje vytváření chyb používáním špatných metod, protože umožní použít jen některé metody
- příklad - pro editaci atributu se vytvoří veřejná metoda a atribut se nastaví jako soukromý

##### 2. Dědičnost

- umožňuje jednotlivým objektům, aby mohly dědit z jiných objektů
- objekt tím předává své vlastnosti dalšímu objektu (mají je společné)
- příklad
  - třída člověk (atributy jméno, věk)
  - třída dospělý - dědí z člověka (atribut práce)
  - třída student - dědí z člověka (atribut škola)
    - dospělý a student mají oba společné atributy jméno a věk ze třídy člověk

##### 3. Polymorfismus

- umožňuje používat jednotné rozhraní pro práci s různými třídami
- pro každou třídu můžeme definovat různé fungování určité metody, kterou mají společnou
- příklad - více zvířat (objektů), každý má svou vlastní metodu pro mluvení, ale každý mluví jinak

![Zvirata](https://www.itnetwork.cz/images/img/polymorphism.gif)

#### Abstraktní třída

- z této třídy nelze vytvářet instance (objekty)
- její jediné využití je, aby jí dědila jiná třída
- nelze vytvořit instanci, protože třída je obecná (např. zvíře)

#### Rozhraní (interface)

- nachází se v něm informace, které má třída obsahovat
- definuje atributy a vlastnosti třídy
- slouží jako "rozpis" dané třídy
- třída může implementovat **více rozhraní současně**, ovšem třída může **dědit pouze z jedné třídy**
