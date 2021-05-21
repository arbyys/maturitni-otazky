## 21 - Návrh webové aplikace ASP.NET
----

#### Razor Pages

- multiplatformní, serverový webový framework
- součástí ecosystému .NET
- využívá:
  - **C#** pro server-side kód
  - Razor syntaxi s HTML kódem, do kterého lze vkládat C# kód
- vhodné pro jednoduché webové stránky
- Razor Pages modifikují MVC, spíše se ovšem podobají MVVM
- spojuje se Controller a View do entity Page-PageModel
- projekt se dělí na:
  - **Model** - data a stav aplikace
  - **ViewModel** - nepovinný - data připravená pro danou stránku
  - **PageModel** - datová a aplikační logika pro danou stránku (Router)
  - **Page** - HTML a Razor syntaxe

#### Page

- samostatná složka `Pages`
- reprezentují koncové body
  - implementace směrování pomocí souborů
- v Page se nachází Razor syntaxe a HTML kód
- v MVC reprezentuje View

#### PageModel

- každá Page má svůj PageModel
- obsahuje logiku a data
- zpracovává HTTP dotazy (`GET`, `POST`)
  - ty poté posílá do View
- v MVC reprezentuje Controller

#### Razor syntaxe

- umožňuje vkládat C# kód do HTML
- kód se zpracuje ještě na serveru, klientovi se posílá dynamicky generovaná stránka
- zapisována do složených závorek za zavináčem - `@{...}`

#### Startup.cs

- do každé aplikace lze přidat určité služby
- nastavuje se v souboru Startup.cs
- obsahuje dvě hlavní metody:
  - **`Configure()`** - nastavuje request pipeline
    - např. `app.UseRouting();`
  - **`ConfigureServices()`** - nastavuje služby, které chceme používat v aplikaci přes Dependency Inejction
    - např. `services.AddRazorPages();`

#### Služba

- samostatné komponenty, které obsahují sdruženou logiku
- lze je znovu použít v jiných aplikacích
- dělají kód přehlednějším
- příklad - Logging service

#### Databáze

- místo, kde jsou uložena data
- k datům se přistupuje přes "SQL dotazy"
- v ASP.NET typicky používan LINQ pro přehlednější dotazy
- připojení k databázi se nastavuje v konfiguračním souboru

#### Entity Framework

- lightweight ORM
- umožňuje jednodušší přístup k databázi
- podporuje velké množství databázových systémů
- umožňuje práci s daty z databáze

#### Identity Framework

- API s logikou pro práci s uživatelskými účty
- má své vlastní UI pro přihlašování
- umí pracovat s uživatelemi, hesly, profilovými daty, claimy, rolemi...
- umožňuje externí přihlášení přes Google, YouTube, Twitter, GitHub...
