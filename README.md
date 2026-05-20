# Valkey Search Workshop

3-hour hands-on workshop building a movie recommendation system with Valkey Search.

## Prerequisites

- A container runtime (Podman, Docker, or Colima)
- Python 3.9+
- Jupyter Notebook

## Windows Setup

### 1. Install a container runtime

**Option A: Podman (recommended, free, no license restrictions)**

Download from https://podman-desktop.io/downloads, then in PowerShell:
```
podman machine init
podman machine start
```

**Option B: Docker Desktop** (free for personal/education use)

Download from https://www.docker.com/products/docker-desktop/

### 2. Install Python + Jupyter

Download Python from https://www.python.org/downloads/ (check "Add to PATH" during install), then:
```
pip install jupyter valkey pandas numpy
```

### 3. Run the workshop

```
cd valkey-search-workshop
jupyter notebook valkey_search_workshop.ipynb
```

---

## Mac Setup

### 1. Install a container runtime

**Option A: Podman (recommended, free, no license restrictions)**
```bash
brew install podman
podman machine init
podman machine start
```

**Option B: Colima (free, open source)**
```bash
brew install docker colima
colima start
```

**Option C: Docker Desktop** (free for personal/education use)

Download from https://www.docker.com/products/docker-desktop/

### 2. Install Jupyter + dependencies

```bash
pip install jupyter valkey pandas numpy
```

### 3. Run the workshop

```bash
cd valkey-search-workshop
jupyter notebook valkey_search_workshop.ipynb
```

This opens the notebook in your browser (usually http://localhost:8888).

### 4. Using the notebook

- Click **Run** (▶) on each cell from top to bottom, or use **Shift+Enter**
- The first cell starts Valkey automatically
- Wait for each cell to finish (the `[*]` becomes `[1]`, `[2]`, etc.) before running the next

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
| 0:00 | Setup | Start Valkey, connect, verify |
| 0:15 | Global Catalog | FT.CREATE, FT.SEARCH, TEXT/TAG/NUMERIC, Vector KNN, Hybrid |
| 1:00 | Single-Slot | Per-user indexes, microsecond queries |
| 1:30 | FT.AGGREGATE | Global user index, GROUPBY, REDUCE, trending |
| 2:00 | End-to-End | Full recommendation pipeline |
| 2:30 | Exercises | Hands-on challenges |

## Cleanup

```bash
podman rm -f valkey    # or: docker rm -f valkey
podman machine stop    # optional
```
