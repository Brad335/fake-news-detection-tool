# Fake News Detection Tool
Structure
fake-news-detection-tool/
│
├── README.md
├── .gitignore
├── docker-compose.yml
├── env.example
│
├── backend/                      ← Member 1 (Backend + NLP)
│   ├── app/
│   │   ├── main.py               # FastAPI app entry point
│   │   ├── api/
│   │   │    └── verify.py        # /verify-claim endpoint
│   │   ├── nlp/
│   │   │    ├── entity_extractor.py
│   │   │    └── similarity.py
│   │   ├── services/
│   │   │    └── verdict_engine.py
│   │   ├── db/
│   │   │    └── database.py      # PostgreSQL connection
│   │   ├── search/
│   │   │    └── opensearch.py    # Search queries
│   │   └── models/
│   │        └── schemas.py       # API request/response models
│   │
│   ├── requirements.txt
│   └── Dockerfile
│
├── data_ingestion/               ← Member 2 (Scraping + Data)
│   ├── rss_fetcher.py            # Reads RSS feeds
│   ├── scraper.py                # Scrapes full article content
│   ├── parser.py                 # Cleans HTML/data
│   ├── storage.py                # Save to PostgreSQL
│   ├── indexer.py                # Push to OpenSearch
│   ├── scheduler.py              # Celery/cron scheduling
│   └── requirements.txt
│
├── frontend/                     ← Member 3 (UI)
│   ├── public/
│   ├── src/
│   │   ├── pages/
│   │   │    └── index.tsx         # Landing page
│   │   ├── components/
│   │   │    ├── ClaimForm.tsx
│   │   │    ├── VerdictCard.tsx
│   │   │    └── EvidenceList.tsx
│   │   ├── services/
│   │   │    └── api.ts           # Calls backend API
│   │   └── styles/
│   │        └── global.css
│   │
│   ├── package.json
│   └── Dockerfile
│
├── scripts/
│   └── run_all.sh                # Start all services locally
│
├── docs/
│   ├── architecture-diagram.png
│   ├── api-spec.md
│   ├── roles-and-workflow.md
│   └── setup-guide.md
│
├── tests/
│   ├── backend/
│   └── ingestion/
│
└── .github/
    └── workflows/
         └── ci.yml               # GitHub Actions pipeline
