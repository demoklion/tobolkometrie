# Návod pro editory - Decap CMS

Jednoduchý návod, jak přidávat a upravovat obsah na webu Tobolkometrie.

## Co je Decap CMS?

Decap CMS je vizuální editor, který vám umožní spravovat obsah webu bez nutnosti znát HTML nebo programování. Funguje jako běžný textový editor (např. Microsoft Word).

## Jak se přihlásit

1. Navštivte adresu: **`https://tobolkometrie.cz/admin/`** (až bude doména aktivní)
2. Klikněte na tlačítko **"Login with GitHub"**
3. Při prvním přihlášení povolte přístup k repozitáři
4. Hotovo! Vidíte administrační rozhraní

## Jak vytvořit nový článek

### Krok za krokem:

1. **V levém menu klikněte na "Články"**
2. **Klikněte na tlačítko "New Článek"** (vpravo nahoře)
3. **Vyplňte formulář:**
   - **Název** - Nadpis článku
   - **Datum publikace** - Vyberte datum (nebo použijte dnešní)
   - **Autor** - Vaše jméno (nebo "Redakce")
   - **Kategorie** - Vyberte z nabídky (Historie, Metodologie, atd.)
   - **Perex** - Krátký úvodní text (1-2 věty) - zobrazí se v seznamu článků
   - **Obrázek** - Volitelné, můžete nahrát ilustrační obrázek
   - **Obsah** - Zde napište celý text článku
   - **Publikováno** - Zaškrtněte, pokud má být článek viditelný

4. **Naformátujte text pomocí nástrojové lišty:**
   - **Tučně** - označte text a klikněte na **B**
   - **Kurzíva** - označte text a klikněte na *I*
   - **Nadpisy** - vyberte úroveň nadpisu (H1, H2, H3)
   - **Seznamy** - odrážky nebo číslované seznamy
   - **Odkazy** - označte text, klikněte na ikonu řetězu, vložte URL

5. **Uložte článek:**
   - **Save** - uloží jako koncept (nikdo ho neuvidí)
   - **Publish** - zveřejní článek na webu

### Příklad struktury článku:

```
Název: Historie knihovnické obce v ČR

Kategorie: Historie

Perex: Krátký přehled vývoje českého knihovnictví od počátku 20. století.

Obsah:
# Hlavní nadpis

Úvodní odstavec s obecným úvodem do tématu...

## Podnadpis - období 1900-1950

Text o tomto období...

### Významné osobnosti

- Zdeněk Václav Tobolka
- Další osobnosti...

## Podnadpis - období 1950-2000

Další text...

**Důležité:** Nějaký zvýrazněný text.
```

## Jak upravit existující článek

1. V levém menu klikněte na **"Články"**
2. Najděte článek v seznamu a **klikněte na něj**
3. Upravte text v editoru
4. Klikněte **"Publish"** pro uložení změn

## Jak vytvořit novou stránku

Stránky jsou pro dlouhodobý obsah (např. "O projektu", "Kontakt").

1. V levém menu klikněte na **"Stránky"**
2. Klikněte **"New Stránka"**
3. Vyplňte:
   - **Název** - Nadpis stránky
   - **URL (slug)** - např. "o-projektu" → stránka bude na adrese `/o-projektu`
   - **Popis** - Krátký popis (pro SEO)
   - **Obsah** - Text stránky
4. Klikněte **"Publish"**

## Jak přidat držitele ceny

1. V levém menu klikněte na **"Držitelé ceny"**
2. Klikněte **"New Držitel ceny"**
3. Vyplňte formulář:
   - **Jméno** - Celé jméno
   - **Rok udělení** - Rok, kdy cenu získal/a
   - **Fotografie** - Nahrát fotografii (volitelné)
   - **Rok narození/úmrtí** - Životní data
   - **Organizace** - Kde působil/a
   - **Pozice** - Jakou měl/a funkci
   - **Město** - Kde působil/a
   - **Odůvodnění ceny** - Proč cenu získal/a
   - **Biografie** - Životopis a přínos oboru
4. Klikněte **"Publish"**

## Jak nahrát obrázek

1. V editoru klikněte na pole **"Obrázek"** nebo **"Fotografie"**
2. Klikněte **"Upload"**
3. Vyberte soubor z počítače
4. Obrázek se automaticky nahraje a zobrazí v článku

**Tip:** Používejte obrázky ve formátu JPG nebo PNG, max. velikost 2 MB.

## Koncept vs. Publikováno

- **Koncept (Save)** - Článek uložíte, ale není viditelný na webu. Můžete ho upravovat.
- **Publikováno (Publish)** - Článek se okamžitě zobrazí na webu.
- **Odškrtnout "Publikováno"** - Článek skryjete z webu, ale zůstane uložený.

## Náhled před publikováním

Bohužel Decap CMS nemá v základu funkci náhledu. Proto doporučujeme:
1. Uložit jako koncept
2. Zkontrolovat text v editoru
3. Publikovat

## Časté dotazy

### Mohu smazat článek?

Ano, otevřete článek a klikněte na tlačítko **"Delete"** v horní liště.

### Co když udělám chybu?

Každá změna je uložena v historii (GitHub). V případě problému lze vrátit předchozí verzi.

### Kolik lidí může upravovat obsah současně?

Více editorů může pracovat najednou, ale nepřepisujte si navzájem stejné články.

### Jak dlouho trvá, než se změny projeví na webu?

Obvykle do **1-2 minut** po kliknutí na "Publish".

## Technická poznámka

Když kliknete na "Publish", Decap CMS automaticky:
1. Uloží váš obsah jako Markdown soubor
2. Vytvoří commit v GitHubu
3. GitHub Pages automaticky aktualizuje web

Není třeba nic dalšího dělat!

## Podpora

Pokud potřebujete pomoc:
- Kontaktujte správce projektu
- Vytvořte Issue na GitHubu projektu
- Email: [kontakt bude doplněn]

---

**Vytvořeno pro projekt Tobolkometrie**
Verze: 1.0 | Datum: 2025-11-06
