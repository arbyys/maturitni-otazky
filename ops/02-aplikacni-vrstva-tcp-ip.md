## 02 - Aplikační vrstva TCP/IP
----

- v TCP / IP jde o jednu vrstvu, v OSI / ISO je to 5., 6. a 7. vstva
- obsahuje protokoly pro aplikace
- protokoly zajišťují výměnu dat po síti
- pro rozlišování protokolů se používají porty
  - některé porty jsou rezervovány pro tyto protokoly


#### Peer-to-Peer (P2P)
- klienti spolu komunikují přímo
- všechny uzly (klienti) jsou si rovnocenné
- jeden klient slouží jako "server" pro jiný klient
- pro co nejrychlejší fungování je nutné mít hodně lidí
- oproti klient-server se méně přetěžuje, méně náchylná vůči výpadkům
- **kryptoměny, torrenty**

#### Klient-server
- klienti komunikují se serverem
- na serveru jsou uchována data
- čím více uživatelů, tím pomalejší přístup
  - zatížení serveru
- oproti P2P bezpečnější, snažší na údržbu, lze aktualizovat data hromadně pro všechny
- **přístup k databázi, emailu**

#### Web server
- počítač, který odpovída za vyřizování HTTP požadavků
- je připojen do sítě
- server vždy vrací odpověď
  - většinou obsahuje HTML dokument / text / obrázek
  - vždy obsahuje hlavičku se stavovým kódem HTTP
    - kód určuje, jak požadavek dopadl

#### Mail server
- přenáší elektronickou poštu z jednoho počítače na jiný

**Odesílaní:**
  - protokol SMTP
    - Simple Mail Transfer Protocol
    - pouze k odesílání

**Získání zpráv:**
  - protokol IMAP
    - Internet Message Access Protocol
    - vyžaduje stálé připojení
    - stahují se pouze nezbytné informace
  - protokol POP3
    - Post Office Protocol
    - nevyžaduje stálé připojení
    - zprávy se po přenesení smažou

#### FTP
- File Transfer Protocol
- **porty 20 a 21**
- transport souborů mezi počítači
- využívá protokol TCP
- uživatelé se ověřují pomocí přihlašovacího protokolu nebo jménem a heslem
- jeden z nejstarších protokolů

#### SMB
- Server Message Block
- slouží ke sdílenému přístupu k souborům / zařízením
- princip klient-server
  - klient posílá požadavek se jménem a heslem

#### Telnet
- Telecommuncation Network
- připojení ke vzdálenému počítači pomocí textového UI
- nešifrovaná komunikace
- využívá protokol TCP
- duplexní spojení, posílá 8bit znaky oběma směry

#### SSH
- Secure Shell
- zabezpečený komunikační protokol
- náhrada za Telnet
- šifrovaná komunikace
- umožňuje přenos dat

#### DHCP
- Dynamic Host Configuration Protocol
- zjednodušení správy sítě
- přiřazuje vhodné IP adresy koncovým zařízením
- tyto adresy se nemusí přiřazovat ručně / přes APIPA
