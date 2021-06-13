## 08 - Návrhové vzory I.
----
NV I. - chovani, vytvareni

- šablony pro řešení konkrétních problémů
- používají se pro zjednodušení daného problému
- snižují možnosti potenciálních chyb
- podobná funkce, jako vzorečky v matematice

#### Druhy návrhových vzorů
1. Vzory chování (behavioral)
    - mění nebo vytváří chování objektů
    - MVC, interpret
2. Strukturální vzory (structural)
    - řeší uspořádání systému a jeho komponent
    - zástupce, prázdný objekt
3. Vzory pro vytváření (creational)
    - zabývají se problémy s tvorbou objektů
    - singleton, pool

#### Tovární metoda (3. - vzory pro vytváření)

- pro vytvoření nové instance třídy na základě určitých parametrů + vnitřní logiky
- může vytvořenou instanci i vracet
- využívá se, když jsou vytvářené objekty odvozeny od stejné třídy
- častý u objektů, jejichž stav nelze po vytvoření změnit

#### Singleton (3. - vzory pro vytváření)

- využíván v případě, že může existovat maximálně jedna instance dané třídy
- samotná instance by měla být přístupná z více míst aplikace
  - centralizovaně dostupná
- musí být vláknově bezpečný a serializovatelný

#### Knihovna (3. - vzory pro vytváření)

- skupina metod, které spolu nějak souvisí
- jsou využívány společně
- třída by neměla být schopna dědit a vytvářet instance (modifikátor static)
- zlepšuje přehlednost kódu a jeho znovupoužitelnost

#### Muší váha - Flyweight (2. - strukturální vzory)

- sdílení prostředků mezi více instancí
- nahrazuje vytváření prostředků pro každou instanci zvlášť
- příklad - textury
- šetří paměťovou náročnost programu
- hra Warcraft

#### Neměnné objekty - Immutable (2. - strukturální vzory)

- hodnotový objekt, u kterého nelze změnit hodnotu
- příklad - string; když se mění jeho hodnota, je vytvořen nový objekt
  - starou instanci poté musí odstranit garbage collector
- absence používání neměnných objektů snižuje bezpečnost programu

#### Přepravka - Crate (2. - strukturální vzory)

- na předávání několika samostatných informací
- řadí se mezi kontejnery
- její atributy mohou být konstatní
- příklad - souřadnice; všechna data (x, y, z) jsou uložena v přepravce

#### Služebník - Servant (1. - vzory chování)

- společná funkčnost pro více objektů, co nemohou mít společného předchůdce
- potřebné objekty se služebníkovi předávají jako parametry
- služebník má definováno určité rozhraní, které musí všechny objekty splňovat
- klient služebníka může, ale nemusí znát
