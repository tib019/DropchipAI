# ADR-001: Docker-Containerisierung für Backend und Frontend

**Status:** Accepted  
**Datum:** 2025

## Kontext
DropchipAI ist eine mehrstufige Anwendung mit Python-Backend (Playwright-Scraping, KI-Logik) und einem Web-Frontend. Deployment auf verschiedenen Umgebungen (Lokal, Render, Produktion) soll reproduzierbar sein.

## Entscheidung
Separate Dockerfiles für Backend (`Dockerfile.backend`) und Frontend (`Dockerfile.frontend`) mit Docker Compose für lokale Orchestrierung.

## Abgewogene Alternativen
- **Monolithischer Container:** Einfacher, aber Frontend/Backend nicht unabhängig skalierbar
- **Kubernetes:** Überdimensioniert für diesen Use Case
- **Direkte VM-Deployment:** Schwieriger reproduzierbar, mehr manuelle Konfiguration

## Konsequenzen
**Positiv:**
- Isolierte Umgebungen für Frontend und Backend
- Einfaches lokales Testing mit `docker compose up`
- Portierbarkeit zwischen Entwicklung und Produktion
- Render.com-Deployment direkt aus Docker-Images

**Negativ:**
- Playwright im Docker-Container benötigt spezielle Browser-Abhängigkeiten
- Build-Zeiten erhöhen sich durch Layer-Aufbau
