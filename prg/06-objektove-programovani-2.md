## 06 - Objektové programování II.
----

#### Zapouzdření

- umožňuje skrýt určité funkce nebo atributy tak, aby byly přístupné pouze uvnitř objektu
  - typicky modifikátory přístupu **private, protected**
- eliminuje vytváření chyb používáním špatných metod, protože umožní použít jen některé metody
- příklad - pro editaci atributu se vytvoří veřejná metoda a atribut se nastaví jako soukromý

#### Dědičnost

- umožňuje jednotlivým objektům, aby mohly dědit z jiných objektů
- objekt tím předává své vlastnosti dalšímu objektu (mají je společné)
- příklad
  - třída člověk (atributy jméno, věk)
  - třída dospělý - dědí z člověka (atribut práce)
  - třída student - dědí z člověka (atribut škola)
    - dospělý a student mají oba společné atributy jméno a věk ze třídy člověk

#### Polymorfismus

- umožňuje používat jednotné rozhraní pro práci s různými třídami
- pro každou třídu můžeme definovat různé fungování určité metody, kterou mají společnou
- příklad - více zvířat (objektů), každý má svou vlastní metodu pro mluvení, ale každý mluví jinak

#### Přepsání a překrytí (overriding)

- jde o implementaci polymorfismu v dědičnosti
- mění chování zděděné metody
- **virtual** - tím deklarujeme metodu, která půjde v děděných třídách přepsat
- **override** - tím deklarujeme metodu, kterou ve zděděné třidě přepisujeme

#### Přetížení (overload)

- umožňuje deklarovat více metod se stejných jménem
- tyto metody se od sebe liší parametry (počet, jméno, pořadí)
- program poté podle počtu zadaných parametrů vybere, kterou z deklarací má použít
