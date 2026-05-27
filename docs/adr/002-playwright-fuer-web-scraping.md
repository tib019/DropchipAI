# ADR-002: Playwright für Web-Scraping und Browser-Automation

**Status:** Accepted  
**Datum:** 2025

## Kontext
DropchipAI benötigt Browser-Automatisierung zum Scrapen von Produktdaten und Preisen von E-Commerce-Websites für KI-gestützte Dropshipping-Analysen.

## Entscheidung
Playwright (Python) wird für Browser-Automation und Web-Scraping verwendet.

## Abgewogene Alternativen
- **Selenium:** Älterer Standard, langsamere API, schlechtere Async-Unterstützung
- **BeautifulSoup/requests:** Kein JavaScript-Rendering, für moderne SPAs ungeeignet
- **Scrapy:** Framework für große Crawl-Operationen, für gezielte Automation überdimensioniert

## Konsequenzen
**Positiv:**
- Unterstützt JavaScript-Heavy-Websites
- Async-Support nativ eingebaut
- Zuverlässige Selector-API (CSS, XPath, Text)
- Headless-Betrieb im Docker-Container möglich

**Negativ:**
- Höherer Ressourcenverbrauch als reine HTTP-Anfragen
- Browser-Binaries im Docker-Image erhöhen Image-Größe deutlich
- Rate-Limiting und Anti-Bot-Maßnahmen können Scraping blockieren
