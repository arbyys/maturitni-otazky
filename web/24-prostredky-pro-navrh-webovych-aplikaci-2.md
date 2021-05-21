## 24 - Prostředky pro návrh webových aplikací II.
----

#### Písmo v WWW

- s roustoucí velikostí monitorů se zvětšovalo i písmo
- doporučená velikost:
  - **14-16px** pro mobil
  - **16-22px** pro desktop
- nutné nalézt ideální hodnoty velikosti písma a řádkování, aby byl text dobře čitelný
- v CSS lze písmu nastavit spoustu vlastností
  - např. velikost, barva, mezery mezi slovy/písmeny, výška řádku atd.

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

##### Vlastnosti CSS

- nastavují se uvnitř složené závorky za selektorem
- ke klíčovým slovům se přiřazuje určitá hodnota
- 520+ různých vlastností

#### Media query

- součást CSS
- představují základní technologii pro responzivní web
- umožňují vytvořit podmínku, která přiřadí rozdílné CSS podle rozlišení obrazovky
- umí také rozpoznat typ zařízení (desktop / mobilní)
- díky tomu lze např. na telefonu nastavit v CSS menší písmo, na desktopu ovšem větší

#### CSS frameworky

- knihovny pro jednodušší použití jazyka CSS na webu
- obsahují:
  - styly pro základní HTML prvky, kterým upravují určité vlastnosti
  - svoje vlastní třídy (komponenty), které lze použít na webu pro jednodušší práci
  - některé obsahují i JavaScript funkcionalitu
- nejznámější je Bootstrap

#### Komponenty v CSS

##### Carousel
- prezentace obrázků, které běží do nekonečna ve smyčce

![Carousel](https://i2.wp.com/cssscript.com/wp-content/uploads/2018/11/Basic-3D-Carousel-In-Pure-JavaScript.png?fit=539%2C401&ssl=1)

##### Collapse
- rozbalovací menu

![Collapse](https://i.stack.imgur.com/OIIst.png)

##### Modal
- vyskakovací okno s informací

![Modal](https://i0.wp.com/cssscript.com/wp-content/uploads/2016/05/simple-responsive-css-modal-dialog.jpg?fit=430%2C316&ssl=1)

##### Tooltip
- většinou zobrazen při najetí myši, obsahuje krátký informační text

![Tooltip](https://raw.githubusercontent.com/alterebro/css-tooltip/HEAD/docs/css-tooltip.png)


#### Možnosti pozicování prvků v Bootstrap

- základní element - `Container`
  - skládají se do něj prvky, lze využít mnoho tříd pro pozicování
  - využití `display: flex;`
- třídy pro `margin` a `padding`
- `Grid` - využívá 12 sloupců, které se přizpůsobí obsahu podle nastavené velikosti:
  - **extra small** (xs)
  - **small** (sm)
  - **medium** (md)
  - **large** (lg)
  - **extra large** (xl)
  - **extra extra large** (xxl)
