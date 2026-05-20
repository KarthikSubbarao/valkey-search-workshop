# Valkey Search Workshop

3-hour hands-on workshop building a movie recommendation system with Valkey Search.

## Prerequisites

- A container runtime (Podman or Docker)
- Python 3.9+
- Jupyter Notebook

## Windows Setup

### 1. Install WSL2 (required for containers)

Open PowerShell **as Administrator** and run:
```powershell
wsl --install --no-distribution
```
**Restart your computer.**

### 2. Install Podman CLI

Open a new PowerShell window:
```powershell
winget install RedHat.Podman
```
Close and reopen PowerShell to refresh the PATH.

### 3. Initialize and start Podman

```powershell
podman machine init
podman machine start
```

### 4. Install Python + Jupyter

Download Python from https://www.python.org/downloads/ (check "Add to PATH" during install), then:
```powershell
pip install jupyter
```

### 5. Run the workshop

```powershell
cd valkey-search-workshop
jupyter notebook valkey_search_workshop.ipynb
```

---

## Linux Setup

### 1. Install Podman (or Docker)

```bash
# Ubuntu/Debian
sudo apt install podman

# Fedora/RHEL
sudo dnf install podman
```

### 2. Install Jupyter

```bash
pip install jupyter
```

### 3. Run the workshop

```bash
cd valkey-search-workshop
jupyter notebook valkey_search_workshop.ipynb
```

---
## Mac Setup

### 1. Install a container runtime

**Option A: Podman (recommended)**
```bash
brew install podman
podman machine init
podman machine start
```

**Option B: Colima + Docker CLI**
```bash
brew install docker colima
colima start
```

**Option C: Docker Desktop**

Download from https://www.docker.com/products/docker-desktop/

### 2. Install Jupyter

```bash
pip install jupyter
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
- Wait for each cell to finish (the `[*]` becomes a number) before running the next

## What's Included

```
workshop/
├── valkey_search_workshop.ipynb    # The workshop notebook
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
