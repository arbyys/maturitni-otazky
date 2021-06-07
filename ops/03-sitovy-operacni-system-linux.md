## 03 - Síťový operační systém – Linux
----

- operační systém
- běží na bázi Unixu
- autor - Linus Torvalds
- licence GNL, Linux je zdarma
- Linux se nevydává jako celek (např. oproti Windows), nýbrž jako hodně malých samostatných programů
- jádro systému - kernel

#### Využití Linuxu
- typicky pro síťové servery
- v kombinaci se serverem Apache
- plní veškeré potřebné funkce pro využití na serveru

#### Distribuce
- open-source distribuce
- liší se vzhledem, HW náročností, balíčkovacím systémem, obsahem
- při vybírání vhodné distribuce je nutné zvážit, na co se bude OS používat
- pro začátečníky je vhodný Linux Mint
- pro pokročilé a náročnější uživatele se hodí Fedora
- většinou je výběr distribuce subjektivní téma
  - podle preferencí a zkušeností

#### Instalace OS
- liší se podle distribuce
- většinou si lze vybrat mezi textovou a grafickou verzí
- kromě OS se nainstaluje i potřebný software k ovládání
  - terminal, prohlížeč...

#### Druhy souborových systémů
- zajišťuje ukládání a čtení dat
- hierarchicky se ukládají v podobě souborů a adresářů
  - jsou unikátní svým jménem
- nejčastější - ext2, ext3, ext4, Btrfs

##### ext2
- second extended filesystem
- open-source
- lze vytvářet speciální druhy souborů, adresáře
- implementován do kernelu v roce 1993

##### ext3
- third extended filesystem
- kompatibilní následník ext2
- komplexní datové struktury, implementace stromů, lze měnit velikost za běhu
- je výchozí souborový systém mnoha distribucí

##### ext4
- fourth extended filesystem
- kompatibilní následník ext3
- zvýšen limit maximální velikosti
- nanosekundová časová razítka, pre-alokace

#### Btrfs
- ve vývoji
- má přinést pokročilé funkce
- důraz na odolnost proti chybám

#### Práva a oprávnění
- udělují se přes příkaz `chmod` v terminalu
- výsledkem je tříciferné číslo
- každá cifra obsahuje číslo, které je součtem hodnot 4, 2 a 1
  - read \(r\) = 4
  - write (w) = 2
  - excute (x) = 1
- první cifra jsou oprávnění **vlastníka**, druhá cifra oprávnění **skupiny** a poslední oprávnění **ostatních**

**Příklady oprávnění:**

![Oprávnění](https://ctrlv.cz/shots/2021/06/03/hjOe.png)

#### Databáze uživatelů a hesel
- informace o uživatelských účtech jsou uloženy v konfiguračních souborech:
  - `/etc/passwd`
  - `/etc/group`
  - `/etc/shadow`
  - `/etc/sudoers`

#### Změna vlastníka a oprávnění
- může provádět pouze administrátor (root)
- příkaz `chown`
- lze měnit vlastníka / skupinu
