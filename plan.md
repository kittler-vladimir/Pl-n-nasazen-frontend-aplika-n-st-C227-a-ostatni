# Plán nasazení – frontend a aplikační část C227

Tým: **Tým A**
Poznámka platná pro všechny úkoly: Prováděno za běhu aplikace C227 v8, není finální verze v9, stále posuny termínů i kvůli řešení nedostatků.

## Pořadí úkolů (logická posloupnost)

| Pořadí | Úkol | Doba trvání | Stav | Plánovaný start | Plánovaný konec |
|---|---|---|---|---|---|
| 1 | Vytvoření zálohy frontend app části (Veritas NetBackup) | 1 hodina | Čekání | 05.06.2026 | 12.06.2026 |
| 2 | Instalace frontend části do Apache 2.4 (servery sezdmz a semdmz) | 1 den | Čekání | 05.06.2026 | 12.06.2026 |
| 3 | Konfigurace Apache (servery sezdmz a semdmz) – nahrání rozcestníku | 1 den | Čekání | 05.06.2026 | 12.06.2026 |
| 4 | Nahrání Java aplikační části C227 | 1 den | Čekání | 05.06.2026 | 12.06.2026 |
| 5 | Rekonfigurace virtuální služby na F5 LB (přístup z internetu a z KIVS) | 1 hodina | Čekání | 05.06.2026 | 12.06.2026 |

## Zdůvodnění pořadí

1. **Záloha** se vytváří jako první, aby existoval bod pro případný rollback ještě před jakýmkoli zásahem.
2. **Instalace frontend části** do Apache je prvním nasazovacím krokem.
3. **Konfigurace Apache** (rozcestník) následuje po instalaci, protože staví na nainstalované frontend části.
4. **Nahrání Java aplikační části** přichází poté, co je frontend funkční a nakonfigurovaný.
5. **Rekonfigurace F5 LB** je poslední krok, který zpřístupní celé řešení uživatelům (internet i KIVS) – dává smysl ji provést až po ověření, že frontend i aplikační část běží.

> Pozn.: Pokud máš informace o závislostech mezi úkoly (např. že LB rekonfigurace musí proběhnout dříve kvůli testování), dej vědět a pořadí upravím.
