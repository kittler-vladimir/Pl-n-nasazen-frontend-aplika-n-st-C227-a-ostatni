# Plán nasazení – AISSE (C227)

Tento repozitář obsahuje plán nasazení frontend a aplikační části systému **C227** (verze v8, příprava na v9).

## Obsah repozitáře

- `plan.md` – plán nasazení s úkoly seřazenými podle logické posloupnosti (záloha → instalace → konfigurace → nahrání aplikace → rekonfigurace LB), včetně odpovědného týmu, stavu a termínů.

## Tým

- **Tým A** – instalace, konfigurace a nasazení frontend a aplikační části

## Poznámka k prostředí

Nasazení probíhá za běhu produkční aplikace C227 v8. Verze v9 zatím není finální, proto mohou nastávat posuny termínů v důsledku řešení nedostatků.

---

## Práce s repozitářem

### Klonování repozitáře

```bash
git clone https://github.com/kittler-vladimir/Plan-nasazeni-AISSE.git
cd Plan-nasazeni-AISSE
```

### Stažení aktuálních změn (pull)

Před každým začátkem práce doporučujeme stáhnout nejnovější verzi z GitHubu:

```bash
git pull origin main
```

Pokud lokální a vzdálená historie nemají společný základ (např. po inicializaci repozitáře s README na GitHubu), použij:

```bash
git pull origin main --allow-unrelated-histories
```

### Odeslání změn (push)

```bash
git add .
git commit -m "Popis provedené změny"
git push origin main
```

Pokud push selže s chybou `non-fast-forward` (vzdálená větev obsahuje commity, které lokálně nemáš), nejprve proveď `git pull origin main` a teprve poté `git push`.

### Práce s Issues

Issues slouží k evidenci úkolů, chyb a návrhů souvisejících s nasazením.

**Vytvoření nového issue (web):**
1. Záložka **Issues** → **New issue**
2. Vyplň název a popis úkolu/problému
3. Nastav přiřazenou osobu (Assignee), štítek (Label) a případně milník (Milestone)

**Vytvoření issue přes GitHub CLI:**
```bash
gh issue create --title "Název úkolu" --body "Popis úkolu" --label bug
```

**Propojení commitu/PR s issue:**
V commit message nebo popisu pull requestu napiš:
```
Fixes #číslo_issue
```
Po sloučení do `main` větve se issue automaticky uzavře.

**Užitečné odkazy v textu:**
- `#12` – odkaz na issue/PR číslo 12
- `@uzivatel` – upozornění konkrétního uživatele v komentáři
- `- [ ] úkol` – checklist v popisu issue (GitHub zobrazí progres, např. 2/5 hotovo)
