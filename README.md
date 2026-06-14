# Petra Zábranská — Správa nemovitostí

Webová administrace realitních nabídek napojená na Supabase (projekt **Petra Reality Web**).
Vše, co se tu uloží, jde do tabulky `nemovitosti` a zobrazí se na webu Petry.

## Obsah repozitáře

| Soubor | Popis |
|---|---|
| `index.html` | Celá aplikace (přihlášení, přehled, přidání/úprava/mazání, nahrávání fotek) |
| `favicon.svg`, `favicon.ico`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | Ikony |
| `manifest.webmanifest` | Umožní „nainstalovat" appku na plochu / mobil |
| `.nojekyll` | Vypne zpracování GitHub Jekyllem (servíruje soubory tak, jak jsou) |

## Nasazení na GitHub Pages (stejně jako CRM)

1. Vytvoř nový repozitář, např. `petra-nemovitosti`.
2. Nahraj do něj **všechny soubory z této složky** (přetažením v GitHubu přes *Add file → Upload files*, nebo `git push`).
3. V repozitáři: **Settings → Pages**.
4. *Source*: **Deploy from a branch**, větev **main**, složka **/ (root)** → **Save**.
5. Za chvíli poběží na adrese:
   `https://TVOJE-JMENO.github.io/petra-nemovitosti/`

> Funguje to i na Netlify / Vercel (jen přetáhneš složku) — kdyby CRM běželo jinde, stejné soubory tam nasadíš stejně.

## Přihlášení

Účet: `petra.zabranska@century21.cz` (heslo nastavené v Supabase).
Zápis (přidat/upravit/smazat nemovitost, nahrát fotky) je možný **jen po přihlášení**.

## Bezpečnost

V `index.html` je uložený **anon (publishable) klíč** Supabase. Ten je určený k zveřejnění — umí
**pouze čtení**. Veškerý zápis je chráněný přihlášením a pravidly RLS v databázi, takže repozitář
může klidně být veřejný.

## Napojení na databázi

- Projekt: `rhdxopvennrbkhkqeqvb` (Petra Reality Web)
- Tabulka: `nemovitosti`
- Bucket na fotky: `nemovitosti_foto` (veřejný pro čtení, nahrávání jen pro přihlášené)
