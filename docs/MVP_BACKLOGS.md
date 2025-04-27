# Mobile FHIR-RAG MVP – Backlog

The table lists **independent, git-reversible microtasks** required to reach the
MVP described in docs/MVP_DESIGN.md.  
Each row ⇒ one PR / branch.

| # | Area | Micro-Task | Key Output |
|---|------|------------|------------|
| 1 | Repo | Initialise monorepo (`mobile/`, `api/`, `infra/`) | `pnpm-workspace.yaml` |
| 2 | CI   | Add ESLint, Prettier, Husky, GitHub Actions | `.github/`, `.eslintrc` |
| 3 | Mobile | Bootstrap React Native (Expo, TS) | `mobile/` scaffold |
| 4 | Mobile | Firebase Auth login flow | `mobile/auth/*.tsx` |
| 5 | API  | Express skeleton + Firebase JWT middleware | `api/src/index.ts` |
| 6 | API  | `/fhir/*` proxy stub to Cloud FHIR Store | `api/src/routes/fhir.ts` |
| 7 | API  | `/rag/search` route returning mock context | `api/src/routes/rag.ts` |
| 8 | Infra | Terraform / SQL schema for pgvector | `infra/sql/001_init.sql` |
| 9 | Pipeline | Chunk-and-embed script (Vertex AI) | `pipeline/embed.ts` |
|10 | Pipeline | Cloud Run job + scheduler YAML | `infra/cloudrun.yaml` |
|11 | API  | Integrate pgvector ANN search (HNSW) | `api/src/services/search.ts` |
|12 | Mobile | Remote embed call + `/rag/search` integration | `mobile/api.ts` |
|13 | Mobile | Native llama.cpp bridge (iOS & Android) | `mobile/native/llama.*` |
|14 | Mobile | Prompt assembly & token streaming | `mobile/llm/useChat.ts` |
|15 | Mobile | Chat UI with cancel/refresh | `mobile/screens/Chat.tsx` |
|16 | Mobile | Citation taps → resource detail view | `mobile/screens/Resource.tsx` |
|17 | Logging | BigQuery audit sink (promptHash etc.) | `api/src/middleware/audit.ts` |
|18 | Resilience | Centralised error handling + fallbacks | `api/src/middleware/error.ts` |
|19 | Perf | p95 tracing & metrics (OpenTelemetry) | `api/src/telemetry.ts` |
|20 | Docs | Update README with run & deploy steps | `README.md` |

> Keep this file updated after each merged PR.
