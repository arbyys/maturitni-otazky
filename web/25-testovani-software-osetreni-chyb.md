## 25 - Testování software, ošetření chyb
----

- chyby mění chování aplikace na abnormální
- neočekávané výsledky algoritmu
- dělí se na syntaktické a sémantické

#### Syntaktické chyby

- jednoduché na odhalení
- většina IDE na ně upozorní ještě před startem programu
  - v případě nekompilovaných jazyků se spustí i s chybou
- jde o např. chybějící středník nebo závorku
  - chyba v zápisu

#### Sémantické chyby

- složité na odhalení a vyřešení
- autor si jich nevšimne na první pohled
- můžou se projevit pouze v určitých případech
- mění chování aplikace, která ovšem jde bez chyb spustit
  - výsledkem je neočekávaný výstup

#### Ladění (debugging)

- metodický postup pro nalezení chyb, popř. snižování jejich množství
- autor nalezne problém, který poté izoluje a opraví ho
- lze využít ladící nástroje v IDE, které usnadňují řešení chyb
  - ukazují kód chyby a jeho možné řešení

#### Výjimky (exceptions)

- používají se jako ochrana před chybným vstupem uživatele
- provedou blok kódu a při chybě ji dokážou detekovat, vrátit a pokračovat v běhu programu
- lze se jim vyhnout pomocí kontroly uživatelova vstupu pomocí podmínek

#### Testování

- proces ověření chování kódu v reakci na určité případy
- prevence chyb
- testy dokáže generovat IDE / jazyk
- zlepšuje kvalitu kódu

##### Jednotkové testy (unit test)
- testuje se pouze jedna určitá komponenta / metoda
