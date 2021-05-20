## 18 - Možnosti pozicování na webových stránkách
----

- tvoření layoutu stránky pozicováním elementů
- nejstarší způsoby - obtékání, tabulky
- moderní způsoby - grid, flex

#### Blokové prvky

- vždy začínají na novém řádku
- využívají plnou šířku, kterou mají k dispozici
- příklad - `<div>...</div>`

#### Inline prvky

- nezačínají na novém řádku - lze jich na jednom řádku mít více vedle sebe
- zabírá pouze takovou šířku, jakou potřebuje
  - neroztahuje se více, než je potřeba
- příklad - `<span>...</span>`

#### Absolutní pozicování

- nastavení přesné hodnoty pozice prvku
  - pomocí souřadnic
- souřadnice v levém horním rohu jsou 0,0
- prvek je umístěn staticky
- prvek ignoruje zbytek stránky (zobrazuje se před ním / za ním)
  - atribut `z-index`

#### Relativní pozicování

- pozice prvku se odvozuje z jiného prvku
- prvek zůstává v dokumentu
- lepší pro respoznivní stránky

#### Obtékání (float)

- prvek obtéká text z určité strany
- již se nepoužívá (na moderních webech)
- obtékaný prvek musí mít danou šířku
- špatné zobrazení na menších displejích

#### Tabulka

- nejstarší a nejvíce zastaralá metoda
- není responzivní
- vymyká se účelu tabulky (zobrazení dat)
- jednoduché na použití
- používají se atributy `colspan` a `rowspan`

#### Flexbox

- všechny prvky uvnitř využívají celé volné místo
- lze nastavit hodně atributů (směr, pozadí, způsob zarovnání)
- vysoká responzivita
- příklad - galerie obrázků

#### Grid

- nejnovější způsob pozicování
- pro celou stránku vytvoří pomyslnou mřížku
  - do ní se umístí jednotlivé prvky
- každá část mřížky má přesně danou funkci - navbar, patička...
- ideálně se používá pro celkový layout stránky

![Grid vs flex](https://ctrlv.cz/shots/2021/05/20/z52U.png)
