# Struktura infra

Na start trzymamy tu tylko rzeczy związane z uruchamianiem całego CodeLobby.

- `local/` — rzeczy do lokalnego developmentu
- `docker/` — Dockerfile i inne pliki kontenerów
- `deployment/` — późniejszy deployment
- `monitoring/` — monitoring i logowanie
- `docs/` — krótkie opisy jak to wszystko odpalić

Sekretów nie wrzucamy do repo. Jak będą potrzebne zmienne środowiskowe, dodamy bezpieczne przykłady typu `.env.example`.
