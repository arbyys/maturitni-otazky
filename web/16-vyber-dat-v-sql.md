## 16 - Výběr dat v SQL
----

#### SELECT

- pro získání informací z tabulky se používá příkaz select
- vrací množinu záznamů z jedné / více tabulek
- v příkazu se specifikuje jaké sloupce chceme získat a z kterých tabulek
- příkaz lze omezit pomocí podmínek `WHERE`

#### Projekce

- určení dat (konkrétních sloupců), které se mají vybírat z databáze

#### Restrikce, podmínky

- `WHERE`
- omezení na určité řádky při výběru dat
- definice podmínek, které musí být při výběru splněny
  - skládají se z logických výrazů, spojek `AND`, `OR`, `NOT` a závorek

#### Agregace

- speciální funkce, které slouží k provádění matematických operací s vybranými daty
- lze vybraná data modifikovat rovnou v SQL
- příklady:
  - `MIN` - minimum
  - `MAX` - maximum
  - `AVG` - průměr
  - `SUM` - suma
  - `COUNT` - počet prvků
  - `ROUND` - zaokrouhlení

#### Části SELECT příkazu

```sql
SELECT jmeno, vek FROM studenti WHERE `vek` > 18 AND COUNT(ukoly) > 30
```

- `jmeno, vek` = **projekce**
- `WHERE ...` = **restrikce**
- `COUNT(ukoly)` = **agregace**

#### Seskupování

- `GROUP BY`
- provádí se podle hodnot určitých sloupců
- odstraňuje duplicity
  - když se najdou dva řádky se stejnou určitou hodnotou, SQL na ně kouká jako na jeden
- typicky použité s agregační funkcí `COUNT`

#### Spojování tabulek

- spojení dvou tabulek do jedné podle určité hodnoty
- dělí se na různé druhy podle stavu společné hodnoty:

##### INNER JOIN
- řádky, co mají stejnou hodnotu v obou tabulkách

##### LEFT JOIN
- všechny řádky z levé tabulky a shodující se vazby z pravé tabulky

##### RIGHT JOIN
- všechny řádky z pravé tabulky a shodující se vazby z levé tabulky

#### FULL OUTER JOIN
- řádky z obou tabulek a doplní NULL při neexistující vazbě

![Typy joinů](https://ctrlv.cz/shots/2021/05/20/iMuC.png)

##### Příklad LEFT JOIN

![Left Join](https://ctrlv.cz/shots/2021/05/20/CSsQ.png)
