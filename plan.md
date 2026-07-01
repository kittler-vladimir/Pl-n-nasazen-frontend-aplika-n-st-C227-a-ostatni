# Plán nasazení – migrace C227 na verzi 9 (AISSE)

---

## 1. Předmigrační přípravné práce na frontend prostředí

| Úkol | Doba trvání | Tým | Poznámka | Stav | Start | Konec |
|---|---|---|---|---|---|---|
| Instalace frontend části do Apache 2.4 (servery sezdmz a semdmz) | 1 den | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze v9, stále posuny termínů i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |
| Konfigurace Apache (servery sezdmz a semdmz) – nahrání rozcestníku | 1 den | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze v9, stále posuny termínů i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |
| Nahrání Java aplikační části C227 | 1 den | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze v9, stále posuny termínů i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |
| Rekonfigurace virtuální služby na F5 LB (přístup z internetu a z KIVS) | 1 hodina | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze v9, stále posuny termínů i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |
| Vytvoření zálohy frontend app části (Veritas NetBackup) | 1 hodina | Tým A | Prováděno zaběhu aplikace C227 v8, není finální verze v9, stále posuny termínů i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |

---

## 2. Předmigrační přípravné práce na backend prostředí

**Pracnost celkem: 7 dnů a 3 hodiny**

| Úkol | Doba trvání | Tým | Poznámka | Stav | Start | Konec |
|---|---|---|---|---|---|---|
| Instalace backend části do Glassfish 5 | 2 dny | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze, i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |
| Vytvoření nových domén C227 (servery semadm a sezadm) | 3 dny | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze, i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |
| Konfigurace nových domén C227 (servery semadm a sezadm) | 2 dny | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze, i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |
| Nahrání Java aplikační části C227 (WAR soubory) | 1 hodina | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze, i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |
| Vytvoření zálohy backend app prostředí pomocí nástrojů Glassfish | 2 hodiny | Tým A | Prováděno za běhu aplikace C227 v8, není finální verze, i kvůli řešení nedostatků, nesplněn termín | Čekání | 05.06.2026 | 12.06.2026 |

---

## 3. Předmigrační přípravné práce na databázovém prostředí

**Pracnost celkem: 7 hodin**

| Úkol | Doba trvání | Tým | Poznámka | Stav | Start | Konec |
|---|---|---|---|---|---|---|
| Vytvoření zálohy Informix instancí CRO, CVDOP a CVDCD (Veritas NetBackup) | 3 hod | Tým A | Prováděno za běhu aplikace C227 v8 | Čekání | 03.07.2026 | – |
| Nahrání migračních scriptů od dodavatele pro úpravu databází | 3 hod | Tým B | Prováděno za běhu aplikace C227 v8 | Čekání | 03.07.2026 | – |
| Přepnutí dotazování PČR na záložní prostředí semdbs122. Bedrunka procedury. | 1 hodina | Tým B | Prováděno za běhu aplikace C227 v8 | Čekání | – | – |

---

## Cutover plán

**Pracnost celkem: 18:50:00 — ČAS T = 9:00, 4.7.2026**

### 4. Migrace prostředí C227 na verzi 9

#### Frontend aplikační část

| Úkol | Doba trvání | Tým | Poznámka | Stav | Datum | Čas začátku | Čas konce |
|---|---|---|---|---|---|---|---|
| Stopnutí Apache 2.2 (servery sezdmz a semdmz) | 10 minut | Tým A | Prováděno paralelně | Čekání | 04.07.2026 | 9:00 | – |
| Rekonfigurace virtuálních služeb na F5 LB (rozdělení memberů v poolu frontend Internet a KIVS) | 30 minut | Tým A | Prováděno paralelně | Čekání | 04.07.2026 | – | – |
| Start Apache 2.4 (servery sezdmz a semdmz) s novou verzí rozcestníků a Java aplikací v9 | 20 minut | Tým A | Prováděno paralelně | Čekání | 04.07.2026 | – | – |
| Kontrola funkčnosti odkazů v DNS (aisse.mvcr.cms2.cz a aisse.mv.gov.cz) | 20 minut | Tým A | Prováděno paralelně | Čekání | 04.07.2026 | – | – |
| Stopnutí Apache 2.4 (servery sezdmz a semdmz) | 10 minut | Tým A | Prováděno paralelně | Čekání | 04.07.2026 | – | 9:30 |
| Vyhodnocení GO/NO GO | 10 minut | Tým A | – | Čekání | 04.07.2026 | 9:30 | 9:40 |

#### Backend aplikační část

| Úkol | Doba trvání | Tým | Dodavatel | Poznámka | Stav | Datum | Čas začátku | Čas konce |
|---|---|---|---|---|---|---|---|---|
| Stopnutí ostatních aplikací a Glassfish domén pracovníky MV ČR (AISSEZR, eOPWS, ePasyWS, policie, atd.) | 10 minut | Tým B | – | Prováděno paralelně | Čekání | 04.07.2026 | 9:40 | – |
| Stopnutí nově vytvořených domén C227 v9 | 15 minut | Tým A | – | Prováděno paralelně | Čekání | 04.07.2026 | – | – |
| Kontrola konfigurace nově vytvořených domén C227 v9 (nastavení portů, certifikátů) | 10 minut | Tým A | – | Prováděno paralelně | – | 04.07.2026 | – | – |
| Nastavení komunikačních bran pro EO, EOP a ECD na relační model v9 | 30 minut | Tým A | – | Prováděno paralelně | – | 04.07.2026 | – | – |
| Nastavení ostatních aplikací a Glassfish domén pracovníky MV ČR (AISSEZR, eOPWS, ePasyWS, policie, atd.) na relační model v9 | – | Tým B | ARICOMA | Prováděno paralelně | – | 04.07.2026 | – | 10:10 |

#### Databázová část

| Úkol | Doba trvání | Tým | Dodavatel | Stav | Datum | Čas začátku | Čas konce |
|---|---|---|---|---|---|---|---|
| Freeze Informix instancí CVS a ZVS v clusteru | 20 minut | Tým A | – | Čekání | 04.07.2026 | 10:10 | – |
| Start migračních SQL scriptů na změnu databází na verzi 9 | 2 hodiny | Tým B + C | d-PROG | Čekání | 04.07.2026 | – | – |
| Konec migračních SQL scriptů na změnu databází na verzi 9, kontrola logů | 30 minut | Tým B | d-PROG | Čekání | 04.07.2026 | – | – |
| Vyhodnocení GO/NO GO | 20 minut | Tým B | d-PROG | Čekání | 04.07.2026 | – | – |
| Unfreeze Informix instancí CVS a ZVS v clusteru | 20 minut | Tým A | – | Čekání | 04.07.2026 | – | 13:40 |

> ✅ **Vyhodnocení databázová část: GO** (migrace DB proběhla úspěšně)

#### Navazující kroky po úspěšné migraci databáze

| Úkol | Doba trvání | Tým | Dodavatel | Poznámka | Stav | Datum | Čas začátku | Čas konce |
|---|---|---|---|---|---|---|---|---|
| Vytvoření zálohy Informix instancí CRO, CVDOP a CVDCD (Veritas NetBackup) | 3 hodiny | Tým A | – | Provádí se automaticky. Pravděpodobně pojede jen záloha CRO, protože ostatní IFX instance se nemění. | Čekání | 04.07.2026 | 13:40 | – |
| Start domén C227 v9 (servery semadm a sezadm) | 30 minut | Tým A | – | – | Čekání | 04.07.2026 | – | – |
| Start komunikačních bran pro EO, EOP a ECD | 1 hodina | Tým A | – | – | Čekání | 04.07.2026 | – | – |
| Start všech ostatních domén a aplikací pracovníky MV ČR (AISSEZR, eOPWS, ePasyWS, policie, atd.) | 1 hodina | Tým B | – | – | Čekání | 04.07.2026 | – | – |
| Start Apache 2.4 (servery sezdmz a semdmz) s novou verzí rozcestníků a Java aplikací v9 | 20 minut | Tým A | – | – | Čekání | 04.07.2026 | – | – |
| Kontrola funkčnosti odkazů v DNS (aisse.mvcr.cms2.cz a aisse.mv.gov.cz) | 10 minut | Tým A+B | – | – | Čekání | 04.07.2026 | – | – |
| Kontrola funkčnosti aplikace verze C227 v9 | 1 hodina | Tým A+B+C | ARICOMA | Provádí Hotline | Čekání | 04.07.2026 | – | – |
| Kontrola funkčnosti komunikačních bran EO, EOP a ECD | 1 hodina | Tým A+B+C | ARICOMA | Provádí Gračko, Mistrík, Schuster, Kittler a Andreáš. Tým A provádět nemůže, nemá povolen přístup k datům. | Čekání | 04.07.2026 | – | – |
| Kontrola funkčnosti všech ostatních domén a aplikací pracovníky MV ČR (AISSEZR, eOPWS, ePasyWS, policie, atd.) | 1 hodina | Tým B+C | ARICOMA | – | Čekání | 04.07.2026 | – | – |
| Vyhodnocení migrace prostředí C227 na verzi 9 GO/NO GO | 30 minut | Tým A+B+C | ARICOMA | – | Čekání | 04.07.2026 | – | – |
| Vyhodnoceno GO | 0 minut | Tým A+B+C | ARICOMA | – | Čekání | 04.07.2026 | – | – |
| Zaslání SMS vedení o ukončení migrace | 10 minut | Tým A+B | – | – | – | 04.07.2026 | – | 22:10 |
