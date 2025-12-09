# Fake News Detection Tool

Monorepo containing:
- backend/     — FastAPI backend, NLP & verdict engine
- data_ingestion/ — scrapers, parser, and indexer
- frontend/    — React/Next frontend
- scripts/     — helper scripts (local startup)
- docs/        — architecture and setup guides
- tests/       — unit & integration tests

Quickstart (local):
1. Copy `.env` from `.env.example` and set values.
2. docker compose up --build
3. Visit frontend at http://localhost:3000 and backend at http://localhost:8000

See docs/setup-guide.md for detailed setup.
