## 17 - Prostředky pro návrh webových aplikací
----

#### HTML

- Hyper Text Markup Language
- v současné době HTML5 (standard od roku 2008)
  - od původní verze HTML se změnily příkazy
- soubory .html, .htm (skoro žádný rozdíl)
- značkovací jazyk (ne programovací)
- tagy ve špičatých závorkách - `<>`
- obsahuje 2 základní části:
  - **hlavička (head)** - informace o stránce, autorovi
  - **tělo (body)** - celý obsah stránky

##### Značka (tag)

- rozlišují typ obsahu, co se v nich nachází
- formátování dokumentu
- párové tagy:
  - `<div>...</div>`
  - `<p>...</p>`
  - `<a>...</a>`
- nepárové tagy:
  - `<hr>`
  - `<br>`
  - `<img>`

##### Atribut

- k tagům lze vkládat atributy (target, href, title)
- definují charakteristiku tagu
- může s nimi pracovat JavaScript

#### CSS

- Cascading Style Sheets
- jazyk pro popis způsobu zobrazení elementů na stránkách
  - pracuje s tagy z HTML
- standardizační organizace W3C
- způsoby implementace:
  - **Internal CSS** - tag `<style></style>` přímo v HTML
    - není potřeba nahrávat více souborů
    - zvětšuje načítací dobu stránky, více kódu v HTML
  - **External CSS** - další .css soubor
    - čistější struktura HTML
    - standard dnešní doby
  - **Inline CSS** - atribut `style=""` přímo v HTML
    - nepřehledný kód
    - používá se většinou při generaci kódu cyklem

![CSS názvosloví](https://ctrlv.cz/shots/2021/05/20/2CtL.png)

##### Selektory

- umožňují označit určité elementy na stránce a nastavit jim styl
- v CSS jednotlivé příkazy začínají vždy selektorem a poté obsahují ve složených závorkách všechny styly
```css
h1{
  font-size: 10px
}
```

- `* {...}` - **hvězdičkový selektor**
  - označuje všechny elementy na stránce
- `E {...}` - **typový selektor**
  - označuje konkrétní element E
- `E[atribut] {...}` - **atributový selektor**
  - označuje všechny elementy E s nastaveným určitým atributem
- `.trida {...}` - **selektor třídy**
  - označuje všechny elementy s určitou třídou
- `#id {...}` - **selektor ID**
  - označuje všechny elementy s určitým ID
- `nth-child()`, `::before`, `::after`, `:hover` ...


#### JavaScript

- objektově orientovaný scriptovací jazyk
- funkce první třídy
  - s funkcemi se zachází jako s jinými proměnnými
  - funkci lze předat jako argument jiným funkcím
- jediný standard dnešní doby pro client-side jazyky na webu
- běží na straně klienta - nebere výkon serveru
- používan pro kontrolu chování webové stránky
  - např. kontrola vstupu od uživatele
