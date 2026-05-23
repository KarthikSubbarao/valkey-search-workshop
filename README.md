# Valkey Search Workshop

3-hour hands-on workshop building a movie recommendation system with Valkey Search.

## Prerequisites

- Git
- Python 3
- A container runtime (Podman or Docker)
- Jupyter Notebook

---

## Setup for Windows

### 1. Install Git and Python

```powershell
winget install --id Git.Git -e --source winget
winget install Python.Python.3
```

Close and reopen PowerShell after installing.

### 2. Install a container runtime

**Podman (recommended, free, no license restrictions):**

First install WSL2 (open PowerShell as Administrator):
```powershell
wsl --install --no-distribution
```
Restart your computer, then:
```powershell
winget install RedHat.Podman
```
Close and reopen PowerShell, then:
```powershell
podman machine init
podman machine start
```

**Or Docker Desktop** (free for personal/education use):
Download from https://www.docker.com/products/docker-desktop/

### 3. Install Jupyter

```powershell
pip install notebook
```

### 4. Clone and run the workshop

```powershell
git clone https://github.com/KarthikSubbarao/valkey-search-workshop.git
cd valkey-search-workshop
python -m notebook valkey_search_workshop.ipynb
```

---

## Setup for macOS

### 1. Install prerequisites

You need `git`, `python3`, and a container runtime. If already installed, skip to step 3.

Using Homebrew:
```bash
brew install git python
```

### 2. Install a container runtime

**Podman (recommended):**
```bash
brew install podman
podman machine init
podman machine start
```

**Or Colima + Docker CLI:**
```bash
brew install docker colima
colima start
```

**Or Docker Desktop:**
Download from https://www.docker.com/products/docker-desktop/

### 3. Install Jupyter

```bash
pip install notebook
```

### 4. Clone and run the workshop

```bash
git clone https://github.com/KarthikSubbarao/valkey-search-workshop.git
cd valkey-search-workshop
python -m notebook valkey_search_workshop.ipynb
```

---

## Setup for Linux

### 1. Install Git, Python, and Podman

```bash
# Ubuntu/Debian
sudo apt install git python3 python3-pip podman

# Fedora/RHEL
sudo dnf install git python3 python3-pip podman
```

### 2. Install Jupyter

```bash
pip install notebook
```

### 3. Clone and run the workshop

```bash
git clone https://github.com/KarthikSubbarao/valkey-search-workshop.git
cd valkey-search-workshop
python -m notebook valkey_search_workshop.ipynb
```

---

## Using the notebook

- Click **Run** (▶) on each cell from top to bottom, or use **Shift+Enter**
- The first cell starts Valkey automatically
- Wait for each cell to finish (the `[*]` becomes a number) before running the next

## What's Included

```
valkey-search-workshop/
├── valkey_search_workshop.ipynb         # Workshop (with exercises)
├── valkey_search_workshop_solved.ipynb  # Reference (with solutions)
├── README.md
└── data/
    ├── catalog.csv                         # Movies with 768-dim vectors
    ├── movies.csv                          # Movie metadata (title, genres, tmdbId)
    ├── ratings.csv                         # User ratings
    └── users.txt                           # Demo user IDs
```

## Cleanup

```bash
podman rm -f valkey    # or: docker rm -f valkey
podman machine stop    # optional
```
