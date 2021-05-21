## 23 - React
----

#### Komponenta

- umožňuje rozdělit UI do částí
- jsou na sobě nezávisle a lze je používat znovu
- typická komponenta - navbar, patička, galerie obrázků
- každá komponenta může přijímat vstup - props

##### Props

- props = properties
- objekt, který slouží jako vstup do komponenty
- přenáší se v něm data, která poté lze použít v komponentě

##### State

- objekt, ve kterém se ukládají vlastnosti do komponenty
- v případě změny state se načítá celá komponenta znovu

#### DOM

- Document Object Model
- rozhraní pro HTML a XML dokumenty
- propojuje více jazyků do jedné stránky
- všechny vlastnosti, metody, události jsou v DOM jako objekty
  - konvertuje webovou stránku na objektově orientovanou

#### Virtual DOM

- rozšíření pro DOM
- koncept, kdy se stav uživatelského rozhraní nejdříve virtuálně uchovává v paměti
  - pokud bude stejný jako námi určený stav, synchronizuje se s knihovnou DOM
- používá se pro optimalizaci rychlosti

#### Událost

- funkce, která se provede při určité akci
  - např. kliknutí na tlačítko
- zapisuje se ve formátu `camelCase`
- funkce se předává jako event handler (ve složených závorkách)
```JavaScript
<button onclick={activateLasers}>
  Activate Lasers
</button>
```
- nelze vracet `false` - místo toho musí vracet metodu `preventDefault()`

#### Hook

- použití různých funkcí Reactu bez použití třídy
  - uvnitř tříd nefunguje
- můžeme díky nim přidat do funkce State bez nutnosti konvertovat na třídu
- **základní hooky:**
  - `useState()`, `useEffect()`, `useContext()`
- **pokročilé hooky:**
  - `useReducer()`, `useMemo()`, `useCallback()`
-
