# Valkey Search Workshop

3-hour hands-on workshop building a movie recommendation system with Valkey Search.

## Prerequisites

- Docker
- Python 3.9+
- Jupyter Notebook

## Mac Setup

### 1. Install Docker

```bash
# Install Docker CLI + Colima (lightweight Docker runtime for Mac)
brew install docker colima

# Start the Docker runtime
colima start

# Verify
docker run --rm hello-world
```

### 2. Install Jupyter + dependencies

```bash
pip install jupyter valkey pandas numpy
```

### 3. Run the workshop

```bash
cd valkey-search-workshop
jupyter notebook valkey_search_workshop.ipynb
```

The first cell in the notebook starts Valkey automatically via Docker.

## What's Included

```
workshop/
├── valkey_search_workshop.ipynb    # The workshop
├── README.md
└── data/
    ├── catalog.csv                 # 1,053 movies with 768-dim vectors
    ├── movies.csv                  # Movie metadata
    ├── ratings.csv                 # 1,958 ratings from 20 users
    ├── links.csv                   # movieId → tmdbId mapping
    └── users.txt                   # Demo user IDs
```

## Workshop Outline

| Time | Section | Topics |
|:-----|:--------|:-------|
| 0:00 | Setup | Docker, connect, verify |
| 0:15 | Global Catalog | FT.CREATE, FT.SEARCH, TEXT/TAG/NUMERIC, Vector KNN, Hybrid |
| 1:00 | Single-Slot | Per-user indexes, microsecond queries |
| 1:30 | FT.AGGREGATE | Global user index, GROUPBY, REDUCE, trending |
| 2:00 | End-to-End | Full recommendation pipeline |
| 2:30 | Exercises | Hands-on challenges |

## Cleanup

```bash
docker rm -f valkey
colima stop  # optional, stops the Docker runtime
```
