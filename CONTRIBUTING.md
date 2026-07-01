# Contributing to StudeQ

StudeQ is a **private, closed-source repository**. This is not an open-contribution project — code access is invite-only.

## Before you do anything

1. Join the [StudeQ Discord](https://demo.com) *(placeholder — replace with real invite link)*.
2. Post in the contributor-access channel with what you'd like to work on.
3. Wait for a maintainer to grant repo access and align scope with you.
4. Once approved, come back here for setup.

**Do not open unsolicited pull requests.** PRs from accounts without prior Discord approval will be closed without review.

All contributors are expected to follow the [Code of Conduct](CODE_OF_CONDUCT.md).

---

## Local Setup

### Prerequisites

- Node.js 22+
- MongoDB (running instance)
- PostgreSQL (running instance)
- Redis (running instance)

### Install

```bash
npm install
```

### Environment

Create `.env.development` (or `.env.production`) in `server/`, based on `.env.example`.

| Variable | Description |
|---|---|
| `PORT` | Server port (default `3000`) |
| `NODE_ENV` | `development` / `production` |
| `LOG_LEVEL` | Winston log level (`info`, `debug`, etc.) |
| `CORS_ORIGINS` | Comma-separated allowed origins, no trailing slash |
| `ACCESS_TOKEN_SECRET` | JWT access token signing secret |
| `ACCESS_TOKEN_EXPIRY` | e.g. `30d` |
| `REFRESH_TOKEN_SECRET` | JWT refresh token signing secret |
| `REFRESH_TOKEN_EXPIRY` | e.g. `60d` |
| `BCRYPT_SALT_ROUNDS` | Password hashing rounds |
| `REFRESH_TOKEN_SALT_ROUNDS` | Refresh token hashing rounds |
| `POSTGRES_URL` | Postgres connection string (Prisma) |
| `MONGO_URI` | MongoDB connection string |
| `MONGO_DB_NAME` | MongoDB database name |
| `MONGO_POOL_SIZE` | Mongo connection pool size |
| `DB_POOL_MAX` | Postgres pool max connections |
| `REDIS_HOST` | Redis host |
| `REDIS_PORT` | Redis port |
| `REDIS_PASSWORD` | `<redis-password>` |
| `GROQ_API_KEY` | Groq LLM API key |
| `GROQ_SUMMARIZE_MODEL` | Model for summarization |
| `GROQ_QUIZ_MODEL` | Model for quiz generation |
| `GROQ_QA_MODEL` | Model for Q&A |
| `GROQ_VISION_MODEL` | Model for vision/OCR tasks |
| `GROQ_RAG_MODEL` | Model for RAG pipeline |
| `NVIDIA_DEEPSEEK_API_KEY` | NVIDIA NIM (DeepSeek) key |
| `NVIDIA_LLAMA_API_KEY` | NVIDIA NIM (Llama) key |
| `PINECONE_API_KEY` | Pinecone vector store key |
| `PINECONE_INDEX_NAME` | Pinecone index name |
| `PINECONE_NAMESPACE` | Pinecone namespace |
| `SERP_API_KEY` | SERP API key (search) |
| `SEARCH_LOCATION` / `SEARCH_HL` / `SEARCH_GL` | Search locale config (default: India / en / in) |
| `UNSPLASH_ACCESS_KEY` | Unsplash image API key |
| `SMTP_USER` / `SMTP_APP_PASSWORD` | Email sending credentials |
| `UPLOAD_DIR` | Upload directory (default `uploads`) |
| `PDF_IMAGES_DIR` | PDF-to-image output dir |
| `MAX_UPLOAD_SIZE_MB` | Max file upload size |
| `VISION_BATCH_SIZE` / `PDF_CONVERT_BATCH_SIZE` | Batch sizes for vision/PDF processing |
| `USER_CACHE_TTL_SECONDS` | User cache TTL |
| `AXIOM_TOKEN` / `AXIOM_DATASET` | Axiom logging observability |
| `RAZORPAY_KEY_ID` / `RAZORPAY_KEY_SECRET` | Razorpay payment credentials |

> Keep the `uploads/` directory present — file upload endpoints depend on it existing.

### Database

```bash
npx prisma generate
npx prisma migrate deploy   # production
npx prisma migrate dev      # local development
```

### Run

```bash
# Terminal 1 — server
cd server
npm run dev

# Terminal 2 — client
cd client
npm run dev
```

### Services Required

- MongoDB — application data
- PostgreSQL — Prisma models
- Redis — BullMQ queues + caching
- Groq / NVIDIA NIM — AI inference
- Razorpay — payments

---

## Codestyle

Backend code must follow the existing conventions in `server/`:

- ESM imports only, named exports
- Route handlers wrapped in `asyncHandler`
- Errors thrown via `ApiError`, responses via `ApiResponse`
- Input validation via Zod `safeParse`
- Mongoose for Mongo models, Prisma for Postgres models — don't mix ORM patterns across DBs
- Background jobs go through BullMQ queues, not inline async work
- Use the existing `logger` (Winston) — no raw `console.log` in server code
- Match existing file/folder naming (controllers, routes, middlewares, validators, services, models, workers)

See `ARCHITECTURE.md` for the full system layout before adding new modules.

## Pull Request Process

1. Branch from `main`: `feat/<short-description>` or `fix/<short-description>`
2. Keep PRs scoped to one feature/fix
3. Ensure `npm run lint` and `npm run build` pass (CircleCI will also check this)
4. Fill in the PR description: what changed, why, how you tested it
5. Tag a maintainer in Discord once opened

## Common Setup Problems

- Missing environment variables — double check `.env.development` against the table above
- MongoDB / PostgreSQL / Redis not running locally
- Prisma migrations not applied (`npx prisma migrate dev`)
- Invalid or missing AI/payment provider API keys

---

See also: [`README.md`](README.md) · [`ARCHITECTURE.md`](ARCHITECTURE.md) · [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)