# Architecture & Component Decisions (Phase 0)

## Frontend
- **Vite + React + Tailwind** for fast dev, simple theming, and small bundles.

## Gateway
- **FastAPI** (REST + WebSockets) for async IO, OpenAPI docs, auth middleware.

## Services
- **Ingest Service**: validates/parses events, writes to ES/OpenSearch, enqueues scoring.
- **Scoring (ML)**: IsolationForest v1 now; pluggable models later; reads/writes via Redis.
- **Rules Worker**: windowed rules (e.g., failed-login burst) producing alerts into Postgres.
- **Incidents Service**: CRUD for incidents, links alerts, permissions.

## Stores
- **PostgreSQL**: metadata, alerts, incidents, users.
- **Elasticsearch/OpenSearch**: logs & aggregates for search and histogram.
- **Redis**: queues (RQ/Sidekiq-style) + caches.
- **MinIO/S3**: attachments, model artifacts.

## Infra
- **Local**: Docker Compose.
- **Later**: Kubernetes, ILM for ES (7d hot / 30d warm / 90d cold).

## Interfaces (high level)
- Gateway → Ingest: `POST /ingest/json` (bulk)
- Gateway → Search: `GET /search`
- Rules Worker → PG: `alerts` table
- Scoring → Redis channels/queues
- Gateway → S3: upload/download artifacts
