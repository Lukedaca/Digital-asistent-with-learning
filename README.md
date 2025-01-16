# Chytrá Asistentka

## Popis
Chytrá Asistentka je Python aplikace, která simuluje digitálního asistenta. Uživatel může s asistentkou komunikovat pomocí textových dotazů a dostávat odpovědi. Program umožňuje asistence učit nové odpovědi na neznámé dotazy a ukládat tyto znalosti pro budoucí použití.

## Funkce
- **Pozdravy:** Asistentka se umí přátelsky uvítát.
- **Základní odpovědi:** Poskytuje informace o aktuálním čase a datu.
- **Učení:** Učí se z interakcí s uživatelem a uloží naučené odpovědi do znalostní báze.
- **Hledání podobných dotazů:** Používá TF-IDF a kosinovou podobnost k vyhledávání podobných otázek ve znalostní bázi.
- **Znalostní báze:** Odpovědi jsou uloženy do souboru `znalosti.json`.

## Použití
1. Spusťte skript pomocí příkazu:
   ```
   python nazev_souboru.py
   ```
2. Asistentka se přívítá a zeptá na vaše dotazy.
3. Zadejte dotaz. Pokud asistentka nezná odpověď, nabídne možnost naučit ji novou odpověď.
4. Pro ukončení komunikace napište `konec`.

## Struktura programu

### Třída `ChytraAsistentka`
- **`__init__`:** Inicializuje jméno asistentky, pozdravy, znalostní bázi a historii konverzace.
- **`load_knowledge`:** Načte uložené znalosti ze souboru `znalosti.json`.
- **`save_knowledge`:** Uloží aktuální znalosti do souboru.
- **`learn_from_interaction`:** Naučí se odpověď na nový dotaz na základě zpětné vazby uživatele.
- **`find_similar_question`:** Hledá podobný dotaz ve znalostní bázi pomocí TF-IDF a kosinové podobnosti.
- **`get_best_response`:** Vybere nejlepší odpověď na základě hodnocení a počtu použití.
- **`odpoved_na_dotaz`:** Generuje odpověď na dotaz uživatele.
- **`get_cas`:** Vrátí aktuální čas.
- **`get_datum`:** Vrátí dnešní datum.

### Funkce `main`
- Inicializuje asistentku.
- Umožňuje uživatelskou interakci prostřednictvím konzole.
- Nabízí možnost naučit se novou odpověď, pokud asistentka odpověď nezná.

## Závislosti
- Python 3.7 a novější
- Knihovny: `random`, `datetime`, `json`, `collections`, `numpy`, `sklearn`

## Formát znalostní báze
Znalosti jsou uloženy v souboru `znalosti.json` ve formátu:
```json
{
  "dotaz": [
    {
      "odpoved": "odpoved",
      "score": 1,
      "pouziti": 1
    }
  ]
}
```

## Další plánované vylepšení
- Rozšíření znalostní báze o různé obory.
- Vylepšení zpracování přirozeného jazyka.
- Možnost exportu a importu znalostní báze.

## Autor
Tento program vytvořil Lukáš Drštička. Program je volně dostupný k dalšímu vývoji a vylepšování.

