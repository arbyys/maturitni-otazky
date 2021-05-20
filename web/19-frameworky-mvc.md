## 19 - Frameworky architektury MVC
----

#### MVC
- Model-View-Controller
- jednotlivé části aplikace se nestarají o zbytek, pouze sami o sebe
  - View a Controller se nemusí starat o to, kde vezme Model data
  - Model se nemusí starat o to, jak se data použijí
- v moderních aplikacích (na webu) používáno společně s routerem
  - router vyhodnocuje URL a na jejich základě předává informace Controlleru

##### Model

- data aplikace

##### View

- uživatelské rozhraní (výstup aplikace)

##### Controller

- logika aplikace - vyhodnotí příkazy a na základě toho požádá model o data, které pošle do View

##### PageModel

- modifikace pro MVC vzor
  - přidává spojení Controlleru a View do jedné entity
    - PageModel - datová a aplikační logika pro stránku
- použit např. ve frameworku ASP.NET

#### MVP

- Model-View-Presenter
- podobné jako MVC
  - místo Controlleru je Presenter
- Presenter reaguje na změnu dat v Modelu a View
- View a Model upozorňuje Presenter v případě změny

#### MVVM

- Model-View-ViewModel

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

#### Request

- klient si požádá o nějaká data
- typicky HTTP request
- dělí se podle metod např. na:
  - `GET` - pro získání dat
  - `POST` - pro nahrání dat
  - `PUT` - pro nahrazení dat
  - `DELETE` - pro smazání dat
  - ...
- vždy vrací výsledek (Response)

#### Response

- výsledek klientova Requestu
- vrací jeden ze stavových kódu HTTP
- dělí se podle kategorií na:
  - `1XX` - **Info**
    - např. `100` - Continue
  - `2XX` - **Success**
    - např. `200` - OK
  - `3XX` - **Redirect**
    - např. `301` - Moved Permanently
  - `4XX` - **Client Error**
    - např. `404` - Not Found
  - `5XX` - **Server Error**
    - např. `500` - Internal Server Error
- společně s HTTP kódem se vrací zároveň i data v případě úspěchu
  - nebo error text v případě chyby
