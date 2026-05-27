# ADR-003: Nginx als Reverse Proxy

**Status:** Accepted  
**Datum:** 2025

## Kontext
Frontend und Backend laufen in separaten Containern. Ein gemeinsamer Einstiegspunkt wird für Routing, CORS-Handling und statisches File-Serving benötigt.

## Entscheidung
Nginx als Reverse Proxy vor Frontend und Backend-Containern.

## Abgewogene Alternativen
- **Traefik:** Dynamischer Proxy, für komplexere Microservice-Setups besser geeignet
- **Direktes Port-Mapping:** Weniger Kontrolle über Routing, CORS-Probleme
- **Caddy:** Einfachere Konfiguration, aber weniger verbreitet im Team

## Konsequenzen
**Positiv:**
- Einheitlicher Einstiegspunkt für alle Requests
- HTTPS-Termination möglich
- Statische Assets können direkt durch Nginx serviert werden

**Negativ:**
- Zusätzliche Konfigurationsebene (`nginx.conf`)
- Bei Konfigurationsfehlern schwer zu debuggen
