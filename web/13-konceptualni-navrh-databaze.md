## 13 - Konceptuální návrh databáze
----

- modelování návrhu databáze
- myšlenkové pochody, abstraktní model situace
- dělí se na tři úrovně
  - konceptální úroveň
  - logická úroveň
  - fyzická úroveň

#### Entita

- jakákoli věc / osoba, která je předmět modelování DB
- dají se pojmenovat
  - **podstatná jména**
- **Entitní typ** - Student
- **Entita** - Jan Novák

#### Atribut

- vlastnosti, co definují entitní typ
  - pouze klíčové informace na entitě, co nás zajímají
- **klíč** - atribut, který definuje entitu
- **kandidátní klíč** - způsob identifikace entity
- **primární klíč** - vybraný kandidátní klíč

#### Relace

- vztahy mezi entitními typy
- dají se pojmenovat
  - **slovesa**

#### Kardinalita

- určuje, kolik entit daného typu se na relaci podílí
- **1 : 1** - one-to-one - člověk a jeho židle
- **1 : N** - one-to-many - student je ve třídě
- **N : M** - many-to-many - knihy a jejich autoři

#### Parcialita
- vyjadřuje povinnost účasti v relaci
- **0** - nepovinná účast (nemandatorní relace)
- **1** - povinná účast (mandatorní relace)

#### Silná entita
- lze ji popsat pomocí jejích atributů
- jednoznačný primární klíč
  - pomocí vlastních atributů

#### Slabá entita
- nelze popsat pomocí jejích atributů
- závisí na **silné entitě**
- nelze vytvořit klíč bez atributů jiné entity

#### Agregace

- vztah celek-část
  - část **může** existovat i bez celku
  - celek není unikátní pro všechny části
- př.: manželství a muž / žena

#### Kompozice

- vztah celek-část
  - část **nemůže** existovat bez celku
  - mezi silnou a slabou entitou
- př.: člověk a jeho ruka
