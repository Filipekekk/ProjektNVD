# Analiza trendów podatności CVE – NVD API
**Autor:** Filip Wójcik  
**Kurs:** Przetwarzanie dużych zbiorów danych – Ścieżka 3 (eksploracja danych)

---

## Struktura projektu

```
projekt_nvd/
├── data/                        # pobrane dane i wykresy (generowane automatycznie)
│   ├── cve_data.csv             # cache pobranych danych
│   ├── wykres_cve_rocznie.png
│   ├── wykres_cve_miesieczny.png
│   ├── wykres_severity.png
│   ├── wykres_severity_rocznie.png
│   ├── wykres_cvss_histogram.png
│   ├── wykres_cwe_top15.png
│   ├── wykres_cwe_trend.png
│   ├── wykres_vendorzy.png
│   └── wykres_vendor_cvss.png
├── notebooks/
│   └── analiza.ipynb            # główny notebook projektu
├── requirements.txt
└── README.md
```

## Instalacja

```bash
pip install -r requirements.txt
```

## Uruchomienie

1. Otwórz `notebooks/analiza.ipynb` w VS Code lub Jupyter
2. Uruchom kolejno wszystkie komórki (Run All)
3. Przy pierwszym uruchomieniu dane zostaną pobrane z NVD API
   - **Bez klucza API:** ~15–30 min (rate limiting 5 req/30s)
   - **Z kluczem API:** ~2–5 min – klucz wstaw w cell #1 (`API_KEY = "twoj-klucz"`)
   - Klucz API (darmowy): https://nvd.nist.gov/developers/request-an-api-key

## Zakres analizy

| # | Analiza |
|---|---------|
| 1 | Trendy czasowe – CVE rocznie i miesięcznie (2015–2024) |
| 2 | Rozkład CVSS Severity (Critical/High/Medium/Low) |
| 3 | Top 15 typów podatności wg CWE |
| 4 | Top 20 vendorów wg liczby CVE + średni CVSS score |

## Źródło danych

- **NVD API v2:** https://services.nvd.nist.gov/rest/json/cves/2.0
- **Dokumentacja API:** https://nvd.nist.gov/developers/vulnerabilities
