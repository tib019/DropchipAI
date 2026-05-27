# Projektscope — DropchipAI

## Problem
Dropshipping-Händler verbringen viele Stunden damit, manuell Produkte auf verschiedenen Plattformen zu recherchieren, Preise zu vergleichen und Marktpotenziale zu bewerten.

## Lösung
DropchipAI automatisiert die Produktrecherche via Browser-Scraping (Playwright) und nutzt KI-Analyse, um Dropshipping-Opportunitäten zu identifizieren und zu bewerten.

## In Scope
- Web-Scraping von E-Commerce-Websites mit Playwright
- KI-gestützte Produktanalyse und Marktbewertung
- Benutzerauthentifizierung (SQLite-Datenbank)
- Web-Frontend für Sucheingaben und Ergebnisanzeige
- Docker-Containerisierung für lokale Entwicklung und Cloud-Deployment
- Nginx als Reverse Proxy
- Deployment auf Render.com

## Out of Scope
- Automatisiertes Bestellen oder Listing auf Verkaufsplattformen
- Integration mit Shopify/WooCommerce-Shops
- Vollständige Multi-User-SaaS-Lösung
- Mobile App

## Sicherheitshinweis
Die Datei `users.db` (SQLite) sollte nicht im Repository liegen. Sie enthält Benutzerdaten und gehört in `.gitignore` bzw. ein separates Volume.

## Technologie-Stack
| Schicht | Technologie |
|---------|-------------|
| Frontend | HTML/CSS, Tailwind CSS, JavaScript |
| Backend | Python (FastAPI/Flask), Playwright |
| Datenbank | SQLite |
| Containerisierung | Docker, Docker Compose |
| Proxy | Nginx |
| Hosting | Render.com |
