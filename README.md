# [echtly Status](https://fatihbektas76.github.io/echtly-uptime/)

Automatischer Uptime-Monitor und Status-Page für [sign.echtly.de](https://sign.echtly.de),
betrieben von [Upptime](https://github.com/upptime/upptime) über GitHub Actions.

Checks laufen alle 5 Minuten (Uptime) und einmal täglich (Antwortzeit + Static Site).

Status-Page: https://fatihbektas76.github.io/echtly-uptime/

## Überwachte Endpoints

- `https://sign.echtly.de/` — Marketing-Startseite
- `https://sign.echtly.de/api/health` — Health-Endpoint der App
- `https://sign.echtly.de/api-docs` — Swagger-UI
- `https://sign.echtly.de/login` — Login-Seite
- `https://sign.echtly.de/impressum` — Rechtspflicht-Seite (DSGVO-relevant)

## Setup-Anleitung

1. Repository auf GitHub erstellen (manuell oder via `gh repo create`).
2. Im Repo-Tab `Settings → Secrets and variables → Actions` einen Secret `GH_PAT`
   anlegen — Personal Access Token (classic) mit Scopes:
   - `repo` (alle Sub-Scopes)
   - `workflow`
3. Im Repo-Tab `Settings → Pages` die Source auf `GitHub Actions` setzen
   (oder `Deploy from a branch: master`, je nach späterem Workflow-Output).
4. Workflow `Setup CI` einmal manuell triggern (`Actions → Setup CI → Run workflow`).
5. Status-Page erscheint nach dem ersten Lauf unter
   `https://fatihbektas76.github.io/echtly-uptime/`.

Erster Check-Lauf wird vom Cron getriggert (alle 5 Min) — kann sofort via
`Actions → Uptime CI → Run workflow` angestoßen werden.
