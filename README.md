ETS_repo

This project is a Python workspace designed to work primarily with Jupyter notebooks in VS Code, using Poetry for dependency management and CSV files as the main data source.

The repository is structured to clearly separate:

exploratory work (notebooks),

reusable Python code,

and local data (not versioned).

Requirements

Before getting started, make sure you have the following installed:

Python 3.11 or higher

Git

Poetry

VS Code (recommended)

VS Code extensions:

Python

Jupyter

1. Clone the repository

Open a terminal and run:

git clone https://github.com/USUARIO/ETS_repo.git
cd ETS_repo

2. Install dependencies with Poetry

This project uses Poetry to manage dependencies and virtual environments.

Run:

poetry install


This command will:

create a virtual environment for the project,

install all required libraries exactly as defined in poetry.lock.

⚠️ You do not need to create a virtual environment manually.

3. Activate or use the Poetry environment

You have two options:

Option A — Activate the environment (recommended for interactive work)
poetry shell

Option B — Run commands explicitly through Poetry
poetry run <command>


Both approaches use the same isolated project environment.

4. Working with notebooks in VS Code

This project is intended to be used directly with notebooks inside VS Code, not in a browser.

Steps:

Open the project folder (ETS_repo) in VS Code

Open or create a notebook in the notebooks/ folder

In the top-right corner of the notebook, select the Kernel

Choose the Python interpreter corresponding to the Poetry environment (usually .venv)

Verify everything works by running the following cell:

import pandas as pd
pd.__version__


If a version number is printed, the environment is correctly configured.

5. Project structure
ETS_repo/
├── notebooks/        # Jupyter notebooks (exploration, analysis)
├── src/ets_repo/     # Reusable Python code
├── data/             # Local CSV data (not versioned)
├── pyproject.toml    # Project configuration (Poetry)
├── poetry.lock       # Locked dependency versions
├── .gitignore
└── README.md

6. Data handling

CSV files should be placed under the data/ directory.

The data/ folder and *.csv files are ignored by Git.

Data is expected to exist locally (e.g. via Dropbox or manual copy).

This keeps the repository lightweight and avoids committing large or sensitive datasets.

7. Important notes

❌ The virtual environment (.venv/) is not committed to GitHub

❌ CSV files in data/ are not versioned

✅ The entire environment can always be recreated with:

poetry install

Recommended workflow (summary)

Pull latest changes from GitHub

Work in notebooks under notebooks/

Move reusable logic into src/ets_repo/

Commit and push code changes (not data, not .venv)