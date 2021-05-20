## 15 - Jazyk SQL
----

- dotazovací jazyk, který pracuje s databází
- jednotlivé SQL příkazy se dělí do kategorií podle jejich kategorie

#### Dialekt

- SQL Server, MySQL, SQLite
- liší se:
  - syntaxí
  - využitím uvozovek
  - rozdílnými příkazy
  - závislostí na velikosti písma (case-sensitive)
- v praxi nejvíce používaný MySQL

#### Standard

- různé standardy jazyka SQL
- navrhuje je ANSI (americký institut)
- aktuální je SQL3
  - před ním byly vydány dvě další verze
- aktuální SQL standard reaguje na objektové potřeby databáze

#### DML

- **Data Manipulation Language**
- manipulace s daty
- `INSERT, UPDATE, DELETE`

#### DDL

- **Data Definition Language**
- definování dat
- `CREATE, DROP, ALTER`

#### DCL

- **Data Control Language**
- nastavování přístupových práv
- `GRANT, REVOKE`

#### TCL

- **Transactional Control Language**
- práce s databázovými transakcemi
- `START TRANSACTION, COMMIT, ROLLBACK`

#### Databázové transakce
- převádí databázi z jednoho konzistentního stavu do druhého
- používají se u databází, které musí pořád běžet
- lze je vrátit (rollback) do původního konzistentního stavu

#### UPDATE

- modifikace existujícího záznamu v tabulce
- upřesňuje se podmínkou `WHERE`
  - tím se učí, které řádky se mají modifikovat

#### INSERT

- přidává do databáze nové záznamy
- bez uvedení konkrétních sloupců se předpokládá vložení celého záznamu
- potřeba uvést hodnoty pro všechny vybrané sloupce
  - počet sloupců = počet hodnot
- lze pomocí něj tabulky kopírovat
