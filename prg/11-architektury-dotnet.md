## 11 - Architektury .NET
----

- framework na tvorbu aplikací pro Windows
- dnes má verze .NET Core a .NET standard
- používané jayky: C#, F#, VB

#### Prostředky architektury .NET pro cílové platformy

##### CLR
- Common Language Runtime
- společné virtuální prostředí, kde běží aplikace
- stará se o správu paměti, typovou kontrolu, výjímky, vlákna, bezpečnost
- jazyky jsou kompilovány do CIL (Common Intermediate Language)

##### FCL

- Framework Class Library
- soubor knihoven integrovaný do CLR
- poskytuje knihovny pro přistup ke konzoli, souborovému systému a pro síťovou konektivitu
- je v něm velké množství knihoven / frameworků pro tvorbu okenních aplikací (WPF, UWP, WinForms)

##### LINQ

- Language Integrated Query
- jednotný jazyk pro dotazování na kolekce
- syntaxe se podobá SQL
- definuje rozšiřující metody, které lze volat pro jednodušší práci s daty

#### MVVM (Model-View-ViewModel)

##### Model

- obsahuje všechnu logiku aplikace a data
- databáze
- neví nic o stavu ovládacích prvků

##### View

- obsahuje uživatelské rozhraní
- okno aplikace / ovládací prvek / stránka
- uživatelsky co nejvíce přívětivý

##### ViewModel

- poskytuje spojení mezi oběma vrstvami
- drží stav aplikace
- ovládací prvky z View jsou pomocí bindingu propojeny s ViewModelem, kde zjišťují svůj obsah
  - rozhraní **INotifyPropertyChanged** - upozorní v případě změny

#### Binding

- svazuje datové zdroje poskytovatele a konzumenta
- sychnronizovaná data
- vlastnosti ViewModelu (poskytovatel) svázány s vlastnostmi vizálních komponent (konzument)
- mechanismus, který při změně dat upozorňuje konzumenty (INotifyPropertyChanged)

#### Command

- objekt, který reprezentuje událost
  - pracuje s delegáty
- volá delegát, který má v sobě uchovaný, pokud nastane určitá událost (event)

#### Converter

- objekt, který přetypovává svázané vlastnosti na jiný typ
- implementuje určité rozhraní (ve WPF `IValue Converter`)
- příklad - string => image

#### Observer
- pozorovatel
- čeká na změnu objektu, poté může reagovat určitým způsobem
- příklad - Binding

#### Událostmi řízené programování
- programovací paradigma
- chod programu řídí události
  - uživatelská akce / změna hodnoty na serveru / obdržení zprávy
- nejvíce se používá v aplikacích s GUI
- využívá naslouchače (event listener) pro detekování určitých akcí
  - v programu běží smyčka, která kontroluje, zda událost nastala
    - pokud nastane, zavolá tzv. callback funkci, která vyvolá akci
