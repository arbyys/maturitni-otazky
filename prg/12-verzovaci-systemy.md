## 12 - Verzovací systémy
----

#### Verzovací systémy

- používán pro správu změn ve zdrojovém kódu software během vývoje
- často používán v projektech, na kterých pracuje více lidí
  - umožňuje řešit kolize v kódu
- eviduje kdo a jak změnil konkrétní řádky kódu
- obsahuje historii celého projektu
- nejrozšířenější verzovací systém = Git
  - distribuovaný systém

#### Git a jeho distribuce

- Git = distribuovaný verzovací systém
- GitHub / GitLab = poskytovatel služby Git na webu
- Git nezaznamenává změny jednotlivých souborů, ale ukládá snapshoty, které obsahují celou kopii všech souborů
- práce na projektu je nejprve lokální - uživatel si až poté změní, které soubory chce nahrát do veřejného repozitáře
  - na projektu lze pracovat i off-line

#### Repozitář (repository)

- datové uložiště verzovacího systému
- dělění:
  - lokální - na PC uživatele
  - vzdálený - na web. poskytovateli (GitHub / GitLab)
- do repozitáře se ukládá kód
- pro vzdálený repozitář se většinou používá název "origin" a pro hlavní větev název "master" / "main"
  - GitHub přechází postupně na "main"

#### Větev (branch)

- posloupnost commitů daného projektu
- každý vzdálený repozitář má min. 1 větev, může jich mít víc
- větve lze spojovat dohromady (merge)
  - díky tomu lze vytvářet různé verze projektu a oddělovat je

#### Další funkce

- **Fork** je vytvoření samostatné kopie repozitáře pro vlastní potřeby
- **Pull request** je žádost o spojení dvou větví dohromady
- **Markdown** je speciální formát textových souborů
  - používá se typicky pro README soubor

#### Git příkazy

##### `git add`
- označí vybrané soubory a připraví je pro nahrání
##### `git commit"`
- uloží vybrané soubory a jejich změny do lokální repozitáře
##### `git push`
- nahraje soubory z lokálního na vzdálený repozitář do určité větve
##### `git clone`
- inicializuje prázdnou složku jako lokální repozitář a stáhne do ní data ze vzdáleného repozitáře
##### `git pull`
- stáhne všechny změny oproti lokálnímu repozitáři ze vzdáleného repozitáře
##### `git fetch`
- podobně jako pull stáhne všechny změny, ovšem nevepíše je do kódu - používáno pro zjištění změn
##### `git diff`
- ukáže rozdíl mezi lokálním a vzdáleným repozitářem
##### `git merge`
- spojí dvě větve dohromady
##### `git init`
- inicializuje složku jako lokální repozitář
