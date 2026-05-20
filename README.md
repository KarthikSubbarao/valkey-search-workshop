# Valkey Search Workshop

3-hour hands-on workshop building a movie recommendation system with Valkey Search.

## Prerequisites

- Docker installed and running
- Python 3.9+

## Quick Start

```bash
pip install jupyter
jupyter notebook valkey_search_workshop.ipynb
```

The notebook handles everything else (starting Valkey, installing deps, loading data).

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
```
