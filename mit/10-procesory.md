## 10 - Procesory
----
#### CPU

- Central Processing Unit
- integrovaný obvod, který provadí strojové instrukce
  - instrukce si načítá z operační paměti a postupně je plní
  - za vteřinu až desítky miliard instrukcí
- procesor pracuje rychleji s vyšší frekvencí, tím se ovšem zvyšuje i teplotní ztráta
- pro každý procesor je nutné vybrat vhodnou patici
  - každých několik generací se udělá nový socket (patice) procesoru
  - ADM a Intel mají odlišné patice
  - Intel 1150, 1151
  - AMD AM4, AM4 plus
- výpočetní technika, chytrá zařízení, pračky
- **části procesoru:**
  - řadič
    - stará se o řízení ostatních jednotek (operační paměť, hard disk)
  - arimeticko-logická jednotka (ALU)
    - provádí operace s čísly a logické operace, je jich v CPU více
  - registry
    - vnitřní paměť, do kterých se ukládají mezivýsledky
    - velmi rychlé
  - paměť cache (vyrovnávací paměť)
    - opětovný přístup k datům z operační paměti
- současné procesory mají:
  - na venek Von Neumannovu architekturu, ovšem na úrovni L1 mají Harvardskou architekturu (RAM, cache)
  - na venek mají architekturu CISC, ovšem uvnitř se rozkládají na RICS instrukce

#### Architektura CPU

##### Architektura instrukční sady
- seznam instrukcí procesoru, datových typů, registrů a pravidla pro fungování procesoru
- definuje počet registrů, syntaxi, způsob ukládání do paměti...
- nemá velký vliv na výkon procesoru
- **x86**
  - podporuje 16bit a 32bit
  - příliš se nepoužívá (kromě Intel Atom)
  - obsahuje variabilní délku instrukcí
  - obsahuje komplexní instrukce (složité)
- **ARM**
  - nízká spotřeba
  - především pro mobilní telefony a podobná zařízení
    - zařízení napájená baterií
  - jednodušší než x86

##### Mikroarchitektura
- způsob, jak je instrukční sada implementována do CPU
- Skylake, Coffee Lake, Kaby Lake

##### x86-64
- rozšířená verze architektury x86
- podporuje až 64bit
- zpětná kompatibilita s 32bit/16bt, zároveň kompatibilní i s 64bit
- na tomto sytému lze tedy instalovat jak 16bit (DOS), 32bit Windows, tak i 64bit Windows
- většinou použita v PC


#### Techniky optimalizace provádění instrukcí

##### Paralelizace
- výkonné jednotky jsou umístěny paraleleně (vedle sebe)
- více jader v procesoru
- lze zpracovávat více instrukcí najednou

##### Fronta instrukcí
- mezi procesorem a operační pamětí se nachází fronta instrukcí
- do fronty se při provádění složitější instrukce mohou skládat další
- procesor nemusí data brát rovnou z operační paměti, která je pomalá
  - další instrukci už si vezme rovnou z fronty, což je rychlejší

##### Paměť cache
- podobně jako u fronty brzdí procesor rychlost operační paměti
- v paměti chache jsou uloženy instrukce pro znovupoužití
- procesory mají několik cache pamětí

##### Provádění instrukcí mimo pořadí
- instrukce jsou prováděny co nejvíce efektivně
- žádné části procesoru nezůstanou nevyužité

#### Snižování spotřeby procesorů
##### Zmenšení výrobní technologie
- menší vzdálenost mezi tranzistory
  - kratší cesta pro elektrony

##### Snížení napájecího napětí
- pokud se sníží napětí, ale zvýší frekvence, procesor bude rychlejší za cenu menšího výkonu

##### Dynamický takt
- procesoru se sníží jeho výkon a spotřeba
- na maximální hranici se poté zvyšuje jen pokud je zrovna potřeba
- Intel **Turbo** Boost / AMD **Turbo** Core

##### Vypínání nevyužitých jader
- čím méně jader se používá, tím menší je spotřeba

##### Vypnutí části cache
- napájí se pouze využívaná část cache

##### HyperThreading
- snížení počtu jader
- vytvoření virtuálních jader

##### SW úroveň
- režim spánku - napájí se pouze RAM
- hibernace - RAM je na disku

#### Rozšířené instrukční sady
- skupina nových instrukcí, které rozšiřují danou instrukční sadu
- přidávají nové jednotky integrovaného obvodu nebo registry
- zvyšují výkon procesoru

##### MMX
- Multi Media Extension
- firma Intel, 1996
- obsahuje SIMD operace pro x86
  - Single Instruction Multiple Data
- nové datové typy
- práce pouze s celými čísly (MMX využívá registrů pro desetinnou čárku)

##### 3DNow!
- firma AMD, 1998
- odpověď na MMX
- umí vše, co MMX
- navíc podporuje desetinná čísla
- za účelem rychlých 3D operací s desetinnými čísly

##### SSE
- Streaming SIMD Extensions
- přidává 128bit registry
- přidává nové instrukce

##### AVX
- Advanced Vector Extensions
- vylepšení SSE
- namísto 128bit registrů přidává 256bit registry
- přidává upravené instrukce pro 256bit

##### x86-64
- rozšíření instrukční sady x86
- přidává kompatibilitu pro 64bit
- ale zároveň zanechává kompatibilitu pro 32bit a 16bit
