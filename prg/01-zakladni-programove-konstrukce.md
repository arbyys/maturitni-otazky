## 01 - Základní programové konstrukce
----

#### Proměnná
- místo v paměti, kam se ukládají data
- musí se v kódu deklarovat
- části:
  - **datový typ** (int / string / float ...)
  - **název** (rezervovaná slova)
  - **hodnota** (odpovídá datovému typu)

#### Datový typ
- **hodnotové** (přímo obsahují proměnnou)
  - **čísla** (int, float, double...)
  - **logické** (bool)
- **referenční** (odkazují na místo v paměti)
  - **class** (object, string ...)
  - **interface**
  - **array**

#### Reference

- odkaz na proměnnou nebo instanci objektu

```Csharp
public int DivideByTwo(int param)
{
  return param / 2;
}
```

#### Hodnota

- entita programu, se kterou může program pracovat

```Csharp
int value = 0;
```

#### Program

- proces projektu, který řídí fungování aplikace
- v C# třída Program

#### Podprogram

- část programu, lze ji opakovaně využívat v programu
- typicky funkce

----

#### Podmínky

- složený příkaz
  - příkazy se provádí za sebou
- příkaz úplný podmíněný (2 větve)
  - **if / else** - pokud platí podmínka, proveď příkaz; jinak proveď příkaz 2
  ```Csharp
    if(c > 0)
    {
      c++;
    }
    else
    {
      c--;
    }
  ```
- příkaz neúplný podmíněný (1 větev)
  - **if** - pokud platí podmínka, proveď příkaz
  ```Csharp
  if(c > 0)
  {
    c++;
  }
  ```

- vícenásobné větvení
  - pokud se hodnota rovná x, proveď příkaz 1; pokud se rovná y, proveď příkaz 2...
  ```Csharp
  switch(c)
  {
    case 1:
      c++;
      break;
    case 0:
      c--;
      break;
    default:
      break;
  }
  ```

#### Cykly

- podmínka na začátku
  - **while** - příkaz nemusí proběhnout, může běžet do nekonečna
  ```Csharp
  int c = 0;

  while (c < 10)
  {
      Console.WriteLine(c);
      c++;
  }
  ```

- podmínka na konci
  - **do-while** - vykonej příkaz, opakuj zda platí podmínka
  ```Csharp
  int c = 0;

  do
  {
    c++;
  } while (c < 10);
  ```

- známý počet průchodů
  - **for** - opakuj tolikrát, kolikrát je zadáno v podmínce
  ```Csharp
  for (int c = 0; c < 10; c++)
  {
    Console.WriteLine(c);
  }
  ```

#### Operátory

- **aritmetické**
  - +, -, *, /
- **logické**
  - &&, ||, !
- **bitové**
  - &, |, ~
- **relační**
  - <, >, ==
- **přístupové**
  - [], ., ()
- **ostatní**
  - =, =>
